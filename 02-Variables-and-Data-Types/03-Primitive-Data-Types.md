# Primitive Data Types in Java

Java provides **eight primitive data types** to store simple values, such as whole numbers, decimal numbers, individual characters, and Boolean values.

Understanding these data types helps you choose the appropriate type for a variable and write efficient, reliable Java programs.

## 1. What Are Primitive Data Types?

Primitive data types are built-in types that store values directly rather than references to objects.

Java has eight primitive data types:

| Data type | Category | Example |
|---|---|---|
| `byte` | Integer | `byte age = 18;` |
| `short` | Integer | `short temperature = 250;` |
| `int` | Integer | `int marks = 95;` |
| `long` | Integer | `long population = 8000000L;` |
| `float` | Floating-point | `float price = 25.5f;` |
| `double` | Floating-point | `double cgpa = 8.75;` |
| `char` | Character | `char grade = 'A';` |
| `boolean` | Boolean | `boolean isPassed = true;` |

These types are grouped into four main categories: integer, floating-point, character, and Boolean.

## 2. Integer Data Types

Java provides four integer types: `byte`, `short`, `int`, and `long`.

They store whole numbers without a fractional part.

### 2.1 byte

The `byte` type uses 8 bits of memory.

- Size: 8 bits (1 byte)
- Range: -128 to 127

Example:

```java
byte age = 18;
byte temperature = -10;

System.out.println(age);
System.out.println(temperature);
```

Output:

```text
18
-10
```

The `byte` type is useful when a small integer range is sufficient.

### 2.2 short

The `short` type uses 16 bits of memory.

- Size: 16 bits (2 bytes)
- Range: -32,768 to 32,767

Example:

```java
short marks = 30000;

System.out.println(marks);
```

Output:

```text
30000
```

### 2.3 int

The `int` type uses 32 bits of memory.

- Size: 32 bits (4 bytes)
- Range: -2,147,483,648 to 2,147,483,647

Example:

```java
int population = 1000000;

System.out.println(population);
```

Output:

```text
1000000
```

`int` is the most commonly used integer type in everyday Java programming.

### 2.4 long

The `long` type uses 64 bits of memory.

- Size: 64 bits (8 bytes)
- Range: -2⁶³ to 2⁶³ - 1

Example:

```java
long distance = 9000000000L;

System.out.println(distance);
```

Output:

```text
9000000000
```

The suffix `L` indicates a long literal. Using uppercase `L` is recommended because lowercase `l` can look like the digit `1`.

## 3. Floating-Point Data Types

Floating-point types represent numbers with fractional parts.

Java provides two floating-point types: `float` and `double`.

### 3.1 float

The `float` type uses 32 bits of memory.

Example:

```java
float price = 25.5f;

System.out.println(price);
```

Output:

```text
25.5
```

The suffix `f` or `F` identifies a floating-point literal as a `float`.

Without the suffix, a decimal literal such as `25.5` is treated as a `double` by default.

A `float` generally provides about 6–7 decimal digits of precision.

### 3.2 double

The `double` type uses 64 bits of memory.

Example:

```java
double cgpa = 8.75;

System.out.println(cgpa);
```

Output:

```text
8.75
```

A `double` generally provides about 15–16 decimal digits of precision.

It is the default type for decimal floating-point literals and is commonly used for calculations involving decimal values.

**Important:** Neither `float` nor `double` represents every decimal number exactly. For financial calculations requiring exact decimal arithmetic, Java provides `BigDecimal`.

## 4. Character Data Type

The `char` type represents a single UTF-16 code unit and uses 16 bits of memory.

Example:

```java
char grade = 'A';
char symbol = '#';

System.out.println(grade);
System.out.println(symbol);
```

Output:

```text
A
#
```

A character literal is written using **single quotation marks**.

```java
char letter = 'A';
```

This is different from a `String`, which uses double quotation marks:

```java
String name = "Java";
```

A `char` can represent a basic character such as `'A'` or a UTF-16 surrogate code unit. Some Unicode characters require two `char` values to represent a complete code point.

## 5. Boolean Data Type

The `boolean` type stores one of two logical values: `true` or `false`.

Example:

```java
boolean isPassed = true;
boolean isRaining = false;

System.out.println(isPassed);
System.out.println(isRaining);
```

Output:

```text
true
false
```

Boolean values are commonly used in conditions and decision-making statements.

For example:

```java
int marks = 75;
boolean passed = marks >= 40;

System.out.println(passed);
```

Output:

```text
true
```

The expression `marks >= 40` evaluates to `true` because `75` is greater than or equal to `40`.

Unlike some other programming languages, Java does not automatically treat `0` or `1` as Boolean values.

## 6. Size and Range Summary

| Type | Size | Range or precision |
|---|---:|---|
| `byte` | 8 bits | -128 to 127 |
| `short` | 16 bits | -32,768 to 32,767 |
| `int` | 32 bits | -2³¹ to 2³¹ - 1 |
| `long` | 64 bits | -2⁶³ to 2⁶³ - 1 |
| `float` | 32 bits | About 6–7 decimal digits of precision |
| `double` | 64 bits | About 15–16 decimal digits of precision |
| `char` | 16 bits | 0 to 65,535 as a UTF-16 code unit |
| `boolean` | Not specified as a storage size by the Java language | `true` or `false` |

The Java language specification defines the ranges of primitive types, but it does not prescribe a particular memory size for a `boolean` variable in every JVM implementation.

## 7. Default Values of Primitive Fields

When primitive variables are declared as instance fields or static fields, Java assigns default values if they are not explicitly initialized.

| Data type | Default value |
|---|---|
| `byte` | `0` |
| `short` | `0` |
| `int` | `0` |
| `long` | `0L` |
| `float` | `0.0f` |
| `double` | `0.0d` |
| `char` | `'\u0000'` |
| `boolean` | `false` |

Example:

```java
public class Main {
    static int number;
    static boolean status;

    public static void main(String[] args) {
        System.out.println(number);
        System.out.println(status);
    }
}
```

Output:

```text
0
false
```

These default values apply to fields. Local variables inside methods do not automatically receive default values and must be assigned before they are read.

## 8. Choosing the Right Primitive Type

Choose a type based on the kind of value you need to represent.

- Use `int` for ordinary whole-number calculations.
- Use `long` for integer values that may exceed the `int` range.
- Use `double` for most general-purpose decimal calculations.
- Use `float` when its lower precision is appropriate or when an API specifically requires it.
- Use `char` for a single UTF-16 code unit.
- Use `boolean` for true-or-false conditions.
- Use `byte` or `short` when their ranges suit the application or when a particular API or data format requires them.

Do not choose a data type based only on its size. Consider its range, precision, and intended use.

## 9. Complete Java Program

```java
public class Main {
    public static void main(String[] args) {
        byte age = 18;
        short year = 2026;
        int marks = 95;
        long population = 8000000000L;

        float temperature = 36.5f;
        double cgpa = 8.75;

        char grade = 'A';
        boolean isPassed = true;

        System.out.println("Age: " + age);
        System.out.println("Year: " + year);
        System.out.println("Marks: " + marks);
        System.out.println("Population: " + population);
        System.out.println("Temperature: " + temperature);
        System.out.println("CGPA: " + cgpa);
        System.out.println("Grade: " + grade);
        System.out.println("Passed: " + isPassed);
    }
}
```

Output:

```text
Age: 18
Year: 2026
Marks: 95
Population: 8000000000
Temperature: 36.5
CGPA: 8.75
Grade: A
Passed: true
```

This program demonstrates all eight primitive data types in one Java class.

## Conclusion

Java has eight primitive data types: `byte`, `short`, `int`, `long`, `float`, `double`, `char`, and `boolean`.

Each type has a particular range or purpose. Choosing an appropriate type helps you represent data correctly and avoid common programming errors.

## Next Topic

Continue with [Reference Data Types in Java](04-Reference-Data-Types.md).
