# The if-else Statement in Java

## 1. Introduction

The `if-else` statement in Java is used when a program needs to choose between two alternatives.

- If the condition is `true`, the `if` block executes.
- If the condition is `false`, the `else` block executes.

Exactly one of these two blocks is selected.

## 2. Syntax

```java
if (condition) {
    // Executes when the condition is true
} else {
    // Executes when the condition is false
}
```

The `else` keyword does not require a separate condition because it handles the alternative case.

## 3. Basic Example

```java
public class Main {
    public static void main(String[] args) {
        int age = 16;

        if (age >= 18) {
            System.out.println("Adult");
        } else {
            System.out.println("Minor");
        }
    }
}
```

**Output:**

```text
Minor
```

**Explanation:**

1. The variable `age` stores `16`.
2. Java checks whether `age >= 18`.
3. The condition is `false`, so the `else` block executes.

## 4. Checking Even and Odd Numbers

The `if-else` statement can determine whether an integer is even or odd.

```java
public class Main {
    public static void main(String[] args) {
        int number = 7;

        if (number % 2 == 0) {
            System.out.println("Even number");
        } else {
            System.out.println("Odd number");
        }
    }
}
```

**Output:**

```text
Odd number
```

**Explanation:**

The remainder operator (`%`) returns the remainder after division.

- If `number % 2 == 0`, the number is even.
- Otherwise, the number is odd.

## 5. Finding the Greater of Two Numbers

```java
public class Main {
    public static void main(String[] args) {
        int a = 25;
        int b = 18;

        if (a > b) {
            System.out.println("a is greater");
        } else {
            System.out.println("b is greater or equal");
        }
    }
}
```

**Output:**

```text
a is greater
```

**Explanation:**

Since `25 > 18` is `true`, Java executes the `if` block.

The `else` message also accounts for the case where both numbers are equal.

## 6. Using if-else with Boolean Variables

A boolean variable stores either `true` or `false`.

```java
public class Main {
    public static void main(String[] args) {
        boolean isRaining = false;

        if (isRaining) {
            System.out.println("Take an umbrella.");
        } else {
            System.out.println("No umbrella is needed.");
        }
    }
}
```

**Output:**

```text
No umbrella is needed.
```

Because `isRaining` is `false`, the `else` block executes.

## 7. Difference Between if and if-else

| `if` statement | `if-else` statement |
|---|---|
| Executes a block when the condition is true. | Chooses between two blocks. |
| Does nothing when the condition is false, then continues. | Executes the `else` block when the condition is false. |
| Useful when an action is needed only in one situation. | Useful when both possible outcomes need handling. |

## 8. Important Points

- The `if` and `else` blocks are alternatives.
- Only one block executes in a single `if-else` statement.
- The condition must evaluate to a boolean value.
- The `else` keyword cannot be used independently; it must be associated with an appropriate `if`.
- Curly braces are recommended even when a block contains only one statement.
- An `if-else` statement can be placed inside another conditional statement when more complex decisions are needed.

## 9. Conclusion

The `if-else` statement helps Java programs choose between two alternative actions. It is useful for handling situations such as checking even or odd numbers, comparing values, and making decisions based on conditions.

## 10. Next Topic

Continue learning with the next topic:

[**The else-if Ladder in Java**](04-else-if-Ladder.md)
