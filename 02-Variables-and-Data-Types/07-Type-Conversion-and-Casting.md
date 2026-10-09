# Type Conversion and Casting in Java

In Java, different data types can represent different kinds of values. Sometimes, we need to convert a value from one data type to another.

This process is called **type conversion** or **type casting**, depending on how the conversion is performed.

Understanding these concepts helps prevent compilation errors and unexpected results in calculations.

## 1. What Is Type Conversion?

Type conversion means changing a value from one data type to another.

For example, we might convert an `int` value into a `double` value.

```java
int number = 10;
double result = number;

System.out.println(result);
```

Output:

```text
10.0
```

Java automatically converts the `int` value to a `double` because the destination type can represent the value without losing its integer information.

## 2. Widening Conversion

**Widening primitive conversion** converts a value from a type with a narrower range or precision to a type that generally has a wider range or precision.

For example:

```java
int number = 25;
double result = number;

System.out.println(number);
System.out.println(result);
```

Output:

```text
25
25.0
```

Java performs this conversion automatically, so an explicit cast is not required.

Common widening primitive conversions include:

- `byte` to `short`, `int`, `long`, `float`, or `double`
- `short` to `int`, `long`, `float`, or `double`
- `char` to `int`, `long`, `float`, or `double`
- `int` to `long`, `float`, or `double`
- `long` to `float` or `double`
- `float` to `double`

Important: Widening does not always guarantee that every numeric value is preserved exactly. For example, converting a large `long` to `float` may lose precision.

## 3. Narrowing Conversion

**Narrowing primitive conversion** converts a value to a type that cannot represent every value of the original type.

Java generally requires an explicit cast for narrowing conversions.

### Example

```java
double price = 99.75;
int wholePrice = (int) price;

System.out.println(price);
System.out.println(wholePrice);
```

Output:

```text
99.75
99
```

The cast `(int)` converts the value to an integer. For finite floating-point values, the fractional part is discarded rather than rounded.

Another example:

```java
int number = 130;
byte result = (byte) number;

System.out.println(result);
```

Output:

```text
-126
```

The result is `-126` because the value `130` is outside the range of `byte`. Narrowing an integer to a smaller integer type keeps the low-order bits, which can produce an unexpected signed value.

## 4. Explicit Type Casting

Type casting means explicitly requesting a conversion using the cast syntax.

### Syntax

```java
targetType variableName = (targetType) value;
```

Example:

```java
double value = 45.89;
int number = (int) value;

System.out.println(number);
```

Output:

```text
45
```

Here, `(int)` explicitly converts the `double` value to an `int`.

Casting can be useful when the programmer understands and accepts the possible loss of information.

## 5. Implicit vs Explicit Conversion

| Feature | Implicit conversion | Explicit conversion |
|---|---|---|
| Also called | Automatic conversion | Casting, when a cast is used |
| Cast required? | Usually no | Yes |
| Example | `double d = 10;` | `int n = (int) 10.5;` |
| Potential information loss | Possible in some widening conversions | Possible in narrowing conversions |

Example of implicit conversion:

```java
int number = 20;
double value = number;
```

Example of explicit conversion:

```java
double value = 20.5;
int number = (int) value;
```

## 6. Type Conversion in Arithmetic Expressions

Java applies numeric promotion when evaluating arithmetic expressions involving primitive numeric types.

For example, `byte`, `short`, and `char` values are generally promoted to `int` during arithmetic operations.

```java
byte a = 10;
byte b = 20;

int sum = a + b;

System.out.println(sum);
```

Output:

```text
30
```

The expression `a + b` produces an `int`, so the result can be assigned to an `int` variable.

This is not valid without a cast:

```java
byte a = 10;
byte b = 20;

// byte sum = a + b; // Compilation error
```

A cast can be used when the programmer ensures the result is within the `byte` range:

```java
byte a = 10;
byte b = 20;

byte sum = (byte) (a + b);

System.out.println(sum);
```

Output:

```text
30
```

## 7. Converting Between Numeric Types and Strings

Primitive numeric conversions and string conversions are different operations.

### Converting a number to a String

Use `String.valueOf()` or string concatenation.

```java
int number = 100;
String text = String.valueOf(number);

System.out.println(text);
```

Output:

```text
100
```

The variable `text` is a `String`, not an `int`.

### Converting a String to an integer

Use `Integer.parseInt()` when the string contains a valid integer representation.

```java
String text = "250";
int number = Integer.parseInt(text);

System.out.println(number);
```

Output:

```text
250
```

If the string does not contain a valid integer representation, `Integer.parseInt()` throws a `NumberFormatException`.

For example, `"hello"` cannot be parsed as an integer.

## 8. Common Mistakes

### Mistake 1: Assigning a double directly to an int

Incorrect:

```java
double value = 12.8;
// int number = value; // Compilation error
```

Correct:

```java
double value = 12.8;
int number = (int) value;
```

The cast makes the narrowing conversion explicit.

### Mistake 2: Assuming casting rounds a decimal

```java
double value = 9.9;
int number = (int) value;

System.out.println(number);
```

Output:

```text
9
```

Casting a finite floating-point value to an integer discards its fractional part; it does not round to the nearest integer.

### Mistake 3: Assuming every widening conversion preserves precision

```java
long number = 123456789012345L;
float result = number;
```

This code compiles, but the `float` value may not preserve the exact original integer because `float` has limited precision.

### Mistake 4: Parsing invalid numeric text

```java
String text = "abc";
// int number = Integer.parseInt(text); // Throws NumberFormatException
```

Ensure the string contains a valid integer representation before parsing it.

## 9. Complete Java Program

```java
public class Main {
    public static void main(String[] args) {
        int number = 25;
        double widened = number;

        double price = 99.75;
        int narrowed = (int) price;

        String text = "150";
        int parsedNumber = Integer.parseInt(text);

        System.out.println("Original integer: " + number);
        System.out.println("Widened double: " + widened);
        System.out.println("Original decimal: " + price);
        System.out.println("Narrowed integer: " + narrowed);
        System.out.println("Parsed integer: " + parsedNumber);
    }
}
```

Output:

```text
Original integer: 25
Widened double: 25.0
Original decimal: 99.75
Narrowed integer: 99
Parsed integer: 150
```

This program demonstrates widening conversion, narrowing conversion, and parsing a numeric string.

## Conclusion

Type conversion allows values to be used with different data types. Widening primitive conversions are generally automatic, while narrowing primitive conversions usually require an explicit cast.

Always consider possible information loss, precision changes, and invalid input when converting values.

## Next Topic

Continue with [Type Promotion in Java](08-Type-Promotion.md).
