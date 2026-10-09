# Introduction to Operators in Java

Operators are special symbols that perform operations on values and variables. They are essential for calculations, comparisons, decision-making, and data manipulation in Java programs.

For example, the `+` operator adds two numbers, while the `>` operator checks whether one value is greater than another.

## 1. What Is an Operator?

An operator performs an operation on one or more operands.

- **Operator:** A symbol that performs an operation.
- **Operand:** A value or variable on which an operator acts.

Example:

```java
int result = 10 + 5;
```

In this statement:

- `10` and `5` are operands.
- `+` is the operator.
- `result` stores the calculated value, `15`.

## 2. Types of Operators in Java

Java provides several categories of operators.

| Operator Type | Purpose | Examples |
|---|---|---|
| Arithmetic | Performs mathematical calculations | `+`, `-`, `*`, `/`, `%` |
| Unary | Operates on a single operand | `++`, `--`, `!`, `-` |
| Relational | Compares two values | `>`, `<`, `>=`, `<=` |
| Equality | Checks whether values are equal or unequal | `==`, `!=` |
| Logical | Combines or reverses Boolean conditions | `&&`, `||`, `!` |
| Assignment | Assigns or updates variable values | `=`, `+=`, `-=` |
| Bitwise | Performs operations on individual bits | `&`, `|`, `^`, `~` |
| Shift | Shifts bits left or right | `<<`, `>>`, `>>>` |
| Ternary | Selects a value based on a condition | `condition ? a : b` |
| Type comparison | Checks an object's type | `instanceof` |

The `+` operator can also concatenate strings, and the `==` operator can compare primitive values or object references, depending on the operands.

## 3. Operators Based on the Number of Operands

Operators can also be classified according to how many operands they use.

### Unary Operators

Unary operators work with one operand.

```java
int number = 5;
number++;
```

After the statement, `number` is `6`.

### Binary Operators

Binary operators work with two operands.

```java
int sum = 10 + 20;
```

The value of `sum` is `30`.

### Ternary Operator

The conditional operator `?:` uses three operands.

```java
int age = 18;
String result = (age >= 18) ? "Adult" : "Minor";
```

The value of `result` is `"Adult"`.

## 4. Example Program

```java
public class Main {
    public static void main(String[] args) {
        int a = 10;
        int b = 5;

        System.out.println("Addition: " + (a + b));
        System.out.println("Greater than: " + (a > b));
        System.out.println("Equal: " + (a == b));
    }
}
```

Output:

```text
Addition: 15
Greater than: true
Equal: false
```

This program demonstrates arithmetic, relational, and equality operators.

## 5. Why Are Operators Important?

Operators allow Java programs to:

- Perform calculations.
- Compare values.
- Evaluate conditions.
- Update variables.
- Manipulate individual bits.
- Choose between alternative values.

They are widely used in conditional statements, loops, methods, and problem-solving programs.

## Conclusion

Operators are a fundamental part of Java programming. Understanding their purpose and behavior makes it easier to write expressions, perform calculations, compare values, and build more complex programs.

## Next Topic

Continue with [Arithmetic Operators in Java](02-Arithmetic-Operators.md) to learn how Java performs mathematical calculations.
