# Operator Precedence and Associativity in Java

## 1. Introduction

When an expression contains multiple operators, Java follows specific rules to determine the order in which the operations are evaluated.

These rules are called **operator precedence** and **operator associativity**.

- **Operator precedence** determines which operator is evaluated first.
- **Operator associativity** determines the evaluation direction when operators have the same precedence.

Understanding these rules helps prevent errors when writing and interpreting Java expressions.

## 2. Operator Precedence

Operator precedence determines the priority of operators in an expression.

For example:

```java
public class Main {
    public static void main(String[] args) {
        int result = 10 + 5 * 2;

        System.out.println(result);
    }
}
```

**Output:**

```text
20
```

**Explanation:**

Multiplication (`*`) has higher precedence than addition (`+`).

Therefore, Java evaluates the expression as:

1. `5 * 2 = 10`
2. `10 + 10 = 20`

It does not evaluate the expression simply from left to right.

## 3. Using Parentheses

Parentheses can be used to change the order of evaluation.

```java
public class Main {
    public static void main(String[] args) {
        int result = (10 + 5) * 2;

        System.out.println(result);
    }
}
```

**Output:**

```text
30
```

**Explanation:**

The expression inside the parentheses is evaluated first.

1. `10 + 5 = 15`
2. `15 * 2 = 30`

Using parentheses can make expressions easier to understand.

## 4. Operator Associativity

Operator associativity determines the order of evaluation when multiple operators have the same precedence.

For example, most arithmetic operators, including subtraction, associate from left to right.

```java
public class Main {
    public static void main(String[] args) {
        int result = 20 - 5 - 3;

        System.out.println(result);
    }
}
```

**Output:**

```text
12
```

**Explanation:**

Subtraction is evaluated from left to right:

1. `20 - 5 = 15`
2. `15 - 3 = 12`

Therefore, the expression is evaluated as `(20 - 5) - 3`.

### Right-to-Left Associativity

Assignment operators associate from right to left.

```java
public class Main {
    public static void main(String[] args) {
        int a, b, c;

        a = b = c = 10;

        System.out.println(a);
        System.out.println(b);
        System.out.println(c);
    }
}
```

**Output:**

```text
10
10
10
```

**Explanation:**

The assignments are evaluated from right to left:

1. `c = 10`
2. `b = c`
3. `a = b`

All three variables receive the value `10`.

## 5. Common Operator Precedence Order

The following table lists common Java operators from higher precedence to lower precedence. Operators within the same row generally have the same precedence.

| Precedence | Operators | Description |
|---|---|---|
| Highest | `()` `[]` `.` | Parentheses, array access, member access |
|  | `expr++` `expr--` | Postfix increment and decrement |
|  | `++expr` `--expr` `!` `~` unary `+` unary `-` | Unary operators |
|  | `*` `/` `%` | Multiplication, division, remainder |
|  | `+` `-` | Addition and subtraction |
|  | `<<` `>>` `>>>` | Shift operators |
|  | `<` `<=` `>` `>=` `instanceof` | Relational operators |
|  | `==` `!=` | Equality operators |
|  | `&` | Bitwise AND |
|  | `^` | Bitwise XOR |
|  | `\|` | Bitwise OR |
|  | `&&` | Logical AND |
|  | `\|\|` | Logical OR |
|  | `?:` | Ternary conditional operator |
|  | `=` `+=` `-=` `*=` `/=` `%=` and other assignments | Assignment operators |
| Lowest | `->` | Lambda expression syntax; handled according to Java's expression grammar |

**Note:** This is a simplified reference table. Java's complete expression grammar includes additional rules, and parentheses can explicitly control evaluation order.

## 6. Example with Multiple Operators

```java
public class Main {
    public static void main(String[] args) {
        int result = 10 + 6 / 2 * 3;

        System.out.println(result);
    }
}
```

**Output:**

```text
19
```

**Explanation:**

Division and multiplication have higher precedence than addition. Division and multiplication associate from left to right.

1. `6 / 2 = 3`
2. `3 * 3 = 9`
3. `10 + 9 = 19`

## 7. Important Points

- Precedence determines which operators have priority.
- Associativity determines grouping when operators share the same precedence.
- Parentheses can change the grouping of an expression.
- Multiplication, division, and remainder have higher precedence than addition and subtraction.
- Assignment operators associate from right to left.
- Precedence and associativity determine how an expression is grouped; they do not guarantee the evaluation order of every operand or subexpression.
- Use parentheses when an expression might otherwise be difficult to understand.

## 8. Conclusion

Operator precedence and associativity are essential concepts for understanding how Java evaluates expressions. Learning these rules helps you write code that is correct, readable, and easier to maintain.

## 9. Next Topic

Continue learning Java with the next topic:

## 9. Next Topic

Continue learning Java with the next topic:

[**Introduction to Conditional Statements in Java**](../04-Conditional-Statements/README.md)
