# Introduction to Conditional Statements in Java

## 1. What Are Conditional Statements?

Conditional statements in Java allow a program to make decisions based on specified conditions.

A condition is an expression that evaluates to either `true` or `false`. Java uses this result to determine which block of code should execute.

For example, a program can check whether a student has passed an examination and display an appropriate message.

## 2. Why Are Conditional Statements Needed?

Without conditional statements, a program generally executes its instructions in sequence. Conditional statements allow the program to choose different actions depending on the situation.

They are useful for:

- Checking whether a number is positive, negative, or zero.
- Determining whether a number is even or odd.
- Checking whether a student has passed an examination.
- Comparing two numbers.
- Selecting an action based on a user's choice.

## 3. Types of Conditional Statements in Java

Java provides several ways to implement conditional logic.

| Statement | Purpose |
|---|---|
| `if` | Executes a block when a condition is true. |
| `if-else` | Chooses between two alternative blocks. |
| `else-if` ladder | Checks multiple conditions in sequence. |
| Nested `if` | Places one `if` statement inside another. |
| `switch` | Selects a branch based on a matching value or supported case pattern. |

Java also supports the ternary operator (`?:`), which is a conditional expression rather than a conditional statement.

## 4. Understanding Conditions

Conditions commonly use relational and logical operators.

Examples of relational operators:

- `==` — equal to
- `!=` — not equal to
- `>` — greater than
- `<` — less than
- `>=` — greater than or equal to
- `<=` — less than or equal to

### Example

```java
public class Main {
    public static void main(String[] args) {
        int age = 20;

        System.out.println(age >= 18);
        System.out.println(age < 18);
    }
}
```

**Output:**

```text
true
false
```

**Explanation:**

- `age >= 18` is `true` because `age` is `20`.
- `age < 18` is `false` because `20` is not less than `18`.

These boolean results can be used in conditional statements.

## 5. A Simple Conditional Example

```java
public class Main {
    public static void main(String[] args) {
        int number = 10;

        if (number > 0) {
            System.out.println("The number is positive.");
        }
    }
}
```

**Output:**

```text
The number is positive.
```

**Explanation:**

1. The variable `number` stores the value `10`.
2. Java checks whether `number > 0`.
3. Since the condition is `true`, the statement inside the `if` block executes.

If the condition were `false`, the block would be skipped.

## 6. General Syntax

A basic conditional statement follows this structure:

```java
if (condition) {
    // Statements executed when the condition is true
}
```

The condition must evaluate to a boolean value (`true` or `false`). Unlike some other programming languages, Java does not treat integers such as `0` or `1` as boolean conditions.

## 7. Important Points

- Conditional statements control the flow of program execution.
- Conditions in Java must evaluate to `boolean`.
- Curly braces `{}` define a block of statements.
- Relational and logical operators are commonly used to form conditions.
- The `if`, `if-else`, `else-if`, nested `if`, and `switch` constructs support different decision-making requirements.
- Clear conditions and consistent indentation make programs easier to understand.

## 8. Conclusion

Conditional statements are a fundamental part of Java programming. They allow programs to make decisions and respond differently to different inputs or situations.

Understanding conditions is the first step toward writing programs that solve problems using decision-making logic.

## 9. Next Topic

Continue learning with the next topic:

[**The `if` Statement in Java**](02-if-Statement.md)
