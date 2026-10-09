# Arithmetic Operators in Java

Arithmetic operators are used to perform mathematical calculations on numeric values and variables. Java provides operators for addition, subtraction, multiplication, division, and finding the remainder.

These operators are commonly used in calculations, formulas, counters, and problem-solving programs.

## 1. Types of Arithmetic Operators

Java provides the following basic arithmetic operators:

| Operator | Name | Description | Example |
|---|---|---|---|
| `+` | Addition | Adds two operands | `10 + 5 = 15` |
| `-` | Subtraction | Subtracts the second operand from the first | `10 - 5 = 5` |
| `*` | Multiplication | Multiplies two operands | `10 * 5 = 50` |
| `/` | Division | Divides the first operand by the second | `10 / 5 = 2` |
| `%` | Modulus | Returns the remainder after division | `10 % 3 = 1` |

## 2. Addition Operator (`+`)

The addition operator adds two numeric values.

```java
int a = 10;
int b = 5;

int sum = a + b;

System.out.println(sum);
```

Output:

```text
15
```

The value of `sum` is `15`.

The `+` operator can also concatenate strings.

```java
String firstName = "Ananya";
String lastName = "Maji";

System.out.println(firstName + " " + lastName);
```

Output:

```text
Ananya Maji
```

## 3. Subtraction Operator (`-`)

The subtraction operator subtracts one value from another.

```java
int a = 20;
int b = 8;

int difference = a - b;

System.out.println(difference);
```

Output:

```text
12
```

The value of `difference` is `12`.

## 4. Multiplication Operator (`*`)

The multiplication operator calculates the product of two numeric values.

```java
int length = 6;
int width = 4;

int area = length * width;

System.out.println(area);
```

Output:

```text
24
```

This example calculates the area of a rectangle.

## 5. Division Operator (`/`)

The division operator divides one value by another.

When both operands are integers, Java performs **integer division**, which discards the fractional part of the result.

```java
int a = 17;
int b = 5;

System.out.println(a / b);
```

Output:

```text
3
```

Although the mathematical result is `3.4`, the result of integer division is `3`.

To obtain a decimal result, use a floating-point operand.

```java
double a = 17.0;
int b = 5;

System.out.println(a / b);
```

Output:

```text
3.4
```

**Important:** Dividing an integer by zero using `/` causes an `ArithmeticException` at runtime. Floating-point division by zero follows different rules and can produce infinity or `NaN`.

## 6. Modulus Operator (`%`)

The modulus operator returns the remainder after division.

```java
int a = 17;
int b = 5;

System.out.println(a % b);
```

Output:

```text
2
```

When `17` is divided by `5`, the quotient is `3` and the remainder is `2`.

### Checking Even and Odd Numbers

The modulus operator is commonly used to check whether an integer is even or odd.

```java
int number = 12;

if (number % 2 == 0) {
    System.out.println("Even");
} else {
    System.out.println("Odd");
}
```

Output:

```text
Even
```

If `number % 2` equals `0`, the number is even. Otherwise, it is odd.

## 7. Arithmetic Operators With Variables

Arithmetic expressions can combine multiple operators.

```java
int a = 10;
int b = 4;

int sum = a + b;
int difference = a - b;
int product = a * b;
int quotient = a / b;
int remainder = a % b;

System.out.println("Sum: " + sum);
System.out.println("Difference: " + difference);
System.out.println("Product: " + product);
System.out.println("Quotient: " + quotient);
System.out.println("Remainder: " + remainder);
```

Output:

```text
Sum: 14
Difference: 6
Product: 40
Quotient: 2
Remainder: 2
```

Notice that `10 / 4` produces `2`, not `2.5`, because both operands are integers.

## 8. Operator Precedence

When an expression contains multiple operators, Java follows precedence rules to determine which operation is evaluated first.

For example:

```java
int result = 10 + 5 * 2;

System.out.println(result);
```

Output:

```text
20
```

Multiplication has higher precedence than addition, so Java evaluates `5 * 2` first and then adds `10`.

Parentheses can change the order of evaluation:

```java
int result = (10 + 5) * 2;

System.out.println(result);
```

Output:

```text
30
```

The expression inside the parentheses is evaluated first.

## Conclusion

Arithmetic operators are essential for performing calculations in Java. Understanding addition, subtraction, multiplication, division, and modulus helps you write programs involving formulas, numeric data, and common coding problems.

## Next Topic

Continue with [Unary Operators in Java](03-Unary-Operators.md) to learn how operators work with a single operand.
