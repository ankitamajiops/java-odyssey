# Type Promotion in Java

Type promotion is a process in Java in which a value of one primitive data type is automatically converted to another type during an expression or operation.

It commonly occurs in arithmetic expressions involving smaller integer types, such as `byte`, `short`, and `char`, and when different numeric types are used together.

Understanding type promotion helps you avoid compilation errors and understand the results of arithmetic expressions.

## 1. What Is Type Promotion?

Type promotion means converting a value to another compatible type during an operation.

For example:

```java
byte a = 10;
byte b = 20;

int result = a + b;

System.out.println(result);
```

Output:

```text
30
```

Although `a` and `b` are declared as `byte`, Java promotes their values to `int` before performing the addition.

Therefore, the expression `a + b` produces an `int` result.

## 2. Promotion of `byte`, `short`, and `char`

In most arithmetic expressions, values of type `byte`, `short`, and `char` are promoted to `int` before the operation.

### Example with `byte`

```java
byte a = 5;
byte b = 10;

int sum = a + b;

System.out.println(sum);
```

Output:

```text
15
```

### Example with `short`

```java
short a = 100;
short b = 200;

int sum = a + b;

System.out.println(sum);
```

Output:

```text
300
```

### Example with `char`

```java
char letter = 'A';

int result = letter + 1;

System.out.println(result);
```

Output:

```text
66
```

The character `'A'` has the numeric value `65` in Java, so adding `1` produces `66`.

The result is an integer, not a character.

## 3. Why Does `byte + byte` Produce an `int`?

Consider this code:

```java
byte a = 10;
byte b = 20;

// byte sum = a + b; // Compilation error
```

This causes a compilation error because the addition expression produces an `int`, which cannot be assigned directly to a `byte` variable without a permitted narrowing conversion.

The correct version is:

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

If you need a `byte` result and know the result is within the `byte` range, you can explicitly cast it:

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

Be careful: casting does not guarantee that a result outside the `byte` range will be preserved correctly.

## 4. Promotion When Different Numeric Types Are Used

When an arithmetic expression contains different numeric types, Java generally promotes the values to a common type.

For binary numeric operations, the general promotion order is:

`double` → `float` → `long` → `int`

The expression is evaluated using the highest applicable type in this order.

### Example 1: `int` and `double`

```java
int a = 10;
double b = 2.5;

double result = a + b;

System.out.println(result);
```

Output:

```text
12.5
```

The `int` value is promoted to `double` before addition.

### Example 2: `int` and `long`

```java
int a = 100;
long b = 200L;

long result = a + b;

System.out.println(result);
```

Output:

```text
300
```

The `int` value is promoted to `long`.

### Example 3: `float` and `double`

```java
float a = 2.5f;
double b = 3.5;

double result = a + b;

System.out.println(result);
```

Output:

```text
6.0
```

The `float` value is promoted to `double` for the operation.

## 5. Type Promotion in Multiplication

Type promotion also occurs during multiplication and other arithmetic operations.

```java
byte a = 4;
byte b = 5;

int product = a * b;

System.out.println(product);
```

Output:

```text
20
```

Both operands are promoted to `int`, and the multiplication produces an `int` result.

The same principle applies to many arithmetic operations involving `byte`, `short`, and `char`.

## 6. Type Promotion and Integer Division

Type promotion can affect division.

Consider:

```java
int a = 5;
int b = 2;

System.out.println(a / b);
```

Output:

```text
2
```

Both operands are integers, so integer division discards the fractional part.

To obtain a decimal result, at least one operand must be converted to a floating-point type before division.

```java
int a = 5;
int b = 2;

double result = (double) a / b;

System.out.println(result);
```

Output:

```text
2.5
```

Here, casting `a` to `double` causes the division to use floating-point arithmetic.

Writing `double result = a / b;` would still produce `2.0`, because the integer division would happen before assignment to `result`.

## 7. Type Promotion in Expressions with `char`

A `char` stores a UTF-16 code unit. When used in an arithmetic expression, it is generally promoted to `int`.

```java
char letter = 'B';

int next = letter + 1;

System.out.println(next);
System.out.println((char) next);
```

Output:

```text
67
C
```

The first output displays the numeric value. The second converts that value back to a `char` before printing it.

This can be useful when performing basic character arithmetic, but Unicode text can involve more complex rules than simple character increments.

## 8. Type Promotion vs Type Casting

| Feature | Type promotion | Type casting |
|---|---|---|
| Meaning | Automatic conversion during an operation | Explicitly requesting a conversion using a cast |
| Common example | `byte + byte` produces `int` | `(int) 5.8` |
| Syntax | Usually no cast needed | Uses `(type)` |
| Possible information loss | Possible for some numeric conversions | Possible when narrowing values |

Example of promotion:

```java
byte a = 5;
byte b = 6;

int result = a + b;
```

Example of casting:

```java
double value = 5.8;
int result = (int) value;
```

Output if printed:

```text
5
```

Type promotion and casting are related, but they are not identical.

## 9. Common Mistakes

### Mistake 1: Assigning an arithmetic result directly to `byte`

Incorrect:

```java
byte a = 10;
byte b = 20;

// byte sum = a + b; // Compilation error
```

Correct:

```java
int sum = a + b;
```

### Mistake 2: Expecting integer division to produce a decimal

Incorrect if a decimal result is expected:

```java
int result = 5 / 2;
System.out.println(result);
```

Output:

```text
2
```

Correct:

```java
double result = 5.0 / 2;
System.out.println(result);
```

Output:

```text
2.5
```

### Mistake 3: Assuming promotion always preserves exact values

Converting a large integer to `float` can lose precision because `float` cannot represent every integer exactly.

```java
long value = 123456789012345L;
float result = value;

System.out.println(result);
```

The printed result may not match the original integer exactly.

## 10. Complete Java Program

```java
public class Main {
    public static void main(String[] args) {
        byte a = 10;
        byte b = 20;

        int sum = a + b;
        int product = a * b;

        int integerDivision = 5 / 2;
        double decimalDivision = (double) 5 / 2;

        char letter = 'A';
        int nextValue = letter + 1;

        System.out.println("Sum: " + sum);
        System.out.println("Product: " + product);
        System.out.println("Integer division: " + integerDivision);
        System.out.println("Decimal division: " + decimalDivision);
        System.out.println("Character numeric value: " + nextValue);
        System.out.println("Next character: " + (char) nextValue);
    }
}
```

Output:

```text
Sum: 30
Product: 200
Integer division: 2
Decimal division: 2.5
Character numeric value: 66
Next character: B
```

This program demonstrates integer promotion, arithmetic expressions, division, and character conversion.

## Conclusion

Type promotion allows Java to evaluate expressions using appropriate numeric types. In particular, `byte`, `short`, and `char` operands are generally promoted to `int` during arithmetic.

Understanding these rules helps you predict expression results and avoid type-related compilation errors.

## Next Topic

Continue with [The `var` Keyword in Java](09-var-Keyword.md).
