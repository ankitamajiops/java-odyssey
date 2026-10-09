# Ternary Operator in Java

## 1. Introduction

The **ternary operator** in Java is a conditional operator that provides a shorter way to choose between two values based on a condition.

It is called the ternary operator because it uses three operands:

1. A condition
2. A value when the condition is `true`
3. A value when the condition is `false`

The ternary operator is represented by `?` and `:`.

## 2. Syntax

```java
condition ? valueIfTrue : valueIfFalse;
```

**How it works:**

- If the condition is `true`, the expression evaluates to `valueIfTrue`.
- If the condition is `false`, the expression evaluates to `valueIfFalse`.

## 3. Simple Example

```java
public class Main {
    public static void main(String[] args) {
        int age = 20;

        String result = (age >= 18) ? "Adult" : "Minor";

        System.out.println(result);
    }
}
```

**Output:**

```text
Adult
```

**Explanation:**

- The condition `age >= 18` is `true`.
- Therefore, the ternary operator selects `"Adult"`.
- The selected value is stored in the `result` variable.

## 4. Ternary Operator with Numbers

```java
public class Main {
    public static void main(String[] args) {
        int a = 15;
        int b = 25;

        int greater = (a > b) ? a : b;

        System.out.println("Greater number: " + greater);
    }
}
```

**Output:**

```text
Greater number: 25
```

**Explanation:**

Since `a > b` is `false`, the operator selects `b`, which is `25`.

## 5. Ternary Operator vs. if-else

Both the ternary operator and `if-else` can make decisions based on conditions.

### Using if-else

```java
int number = 7;
String result;

if (number % 2 == 0) {
    result = "Even";
} else {
    result = "Odd";
}

System.out.println(result);
```

### Using the ternary operator

```java
int number = 7;

String result = (number % 2 == 0) ? "Even" : "Odd";

System.out.println(result);
```

**Output for both programs:**

```text
Odd
```

The ternary operator is useful when a simple condition selects one of two values. For more complex logic, `if-else` is usually easier to read.

## 6. Using the Ternary Operator Directly

The result of a ternary expression can be printed directly.

```java
public class Main {
    public static void main(String[] args) {
        int number = 12;

        System.out.println(
            (number > 10) ? "Greater than 10" : "10 or less"
        );
    }
}
```

**Output:**

```text
Greater than 10
```

## 7. Nested Ternary Operators

A ternary operator can be placed inside another ternary expression. This is called a **nested ternary operator**.

```java
public class Main {
    public static void main(String[] args) {
        int number = 0;

        String result = (number > 0)
                ? "Positive"
                : (number < 0 ? "Negative" : "Zero");

        System.out.println(result);
    }
}
```

**Output:**

```text
Zero
```

**Explanation:**

- First, Java checks whether `number > 0`.
- Since the condition is `false`, it evaluates the second ternary expression.
- The condition `number < 0` is also `false`, so the result is `"Zero"`.

Nested ternary expressions should be used carefully because too many levels can make code difficult to understand.

## 8. Important Points

- The ternary operator uses three operands.
- The symbols `?` and `:` are used in its syntax.
- It evaluates a condition and selects one of two expressions.
- It can be used to assign a value to a variable or as part of another expression.
- Both possible results must be compatible with the context in which the expression is used.
- Use `if-else` when the logic is complex or readability would otherwise suffer.

## 9. Conclusion

The ternary operator is a concise way to write simple conditional expressions in Java. Understanding it helps make short decision-making expressions easier to write and read.

## 9. Next Topic

Continue learning Java operators in the next topic:

[**Instanceof Operator in Java**](10-Instanceof-Operator.md)
