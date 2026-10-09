# The if Statement in Java

## 1. Introduction

The `if` statement is one of the most basic conditional statements in Java. It executes a block of code only when a specified condition evaluates to `true`.

If the condition is `false`, Java skips the block and continues executing the program.

## 2. Syntax

```java
if (condition) {
    // Code executed when the condition is true
}
```

Here:
- `if` is the keyword used to begin the conditional statement.
- `condition` is an expression that evaluates to `true` or `false`.
- The code inside the braces executes only when the condition is `true`.

## 3. Basic Example

```java
public class Main {
    public static void main(String[] args) {
        int age = 20;

        if (age >= 18) {
            System.out.println("You are eligible to vote.");
        }
    }
}
```

**Output:**

```text
You are eligible to vote.
```

**Explanation:**

1. The variable `age` stores the value `20`.
2. Java checks whether `age >= 18`.
3. Since the condition is `true`, the message is printed.

## 4. Example When the Condition Is False

```java
public class Main {
    public static void main(String[] args) {
        int number = 5;

        if (number < 0) {
            System.out.println("The number is negative.");
        }

        System.out.println("Program completed.");
    }
}
```

**Output:**

```text
Program completed.
```

**Explanation:**

The condition `number < 0` is `false` because `number` is `5`. Therefore, Java skips the `if` block and prints only `Program completed.`

## 5. Using Relational Operators

Relational operators are commonly used in `if` conditions.

```java
public class Main {
    public static void main(String[] args) {
        int a = 15;
        int b = 10;

        if (a > b) {
            System.out.println("a is greater than b.");
        }

        if (a != b) {
            System.out.println("a and b are different.");
        }
    }
}
```

**Output:**

```text
a is greater than b.
a and b are different.
```

Both conditions are `true`, so both messages are printed.

## 6. Using Logical Operators

Logical operators can combine multiple conditions.

```java
public class Main {
    public static void main(String[] args) {
        int age = 20;
        boolean hasID = true;

        if (age >= 18 && hasID) {
            System.out.println("Conditions satisfied.");
        }
    }
}
```

**Output:**

```text
Conditions satisfied.
```

**Explanation:**

The `&&` operator means logical AND. Both conditions must be `true` for the entire expression to be `true`.

## 7. The Importance of Curly Braces

Curly braces group statements into a block. They are especially important when multiple statements need to execute under the same condition.

```java
public class Main {
    public static void main(String[] args) {
        int number = 10;

        if (number > 0) {
            System.out.println("Positive number.");
            System.out.println("The condition is true.");
        }
    }
}
```

**Output:**

```text
Positive number.
The condition is true.
```

Even when an `if` statement contains only one statement, using braces consistently improves readability and helps prevent mistakes when the code is modified later.

## 8. Important Points

- The `if` statement executes its block only when the condition is `true`.
- The condition must evaluate to a `boolean` value.
- If the condition is `false`, the block is skipped.
- Relational and logical operators are frequently used in conditions.
- Curly braces define the block of code controlled by the condition.
- Java is case-sensitive, so the keyword must be written as `if`, not `If` or `IF`.

## 9. Conclusion

The `if` statement allows a Java program to execute code selectively based on a condition. It is a fundamental building block for decision-making and more complex conditional logic.

## 10. Next Topic

Continue learning with the next topic:

[**The if-else Statement in Java**](03-if-else-Statement.md)
