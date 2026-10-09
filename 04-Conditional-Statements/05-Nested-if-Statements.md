# Nested if Statements in Java

## 1. Introduction

A **nested `if` statement** is an `if` statement placed inside another `if` statement or inside another conditional block.

Nested `if` statements are useful when a decision depends on more than one condition, and one condition needs to be checked only after another condition is satisfied.

## 2. Syntax

```java
if (condition1) {
    if (condition2) {
        // Executes when both conditions are true
    }
}
```

**How it works:**

1. Java checks `condition1`.
2. If `condition1` is `true`, Java enters the outer block.
3. Java then checks `condition2`.
4. The inner block executes only if `condition2` is also `true`.

If the outer condition is `false`, the inner `if` statement is skipped.

## 3. Basic Example

```java
public class Main {
    public static void main(String[] args) {
        int age = 20;
        boolean hasID = true;

        if (age >= 18) {
            if (hasID) {
                System.out.println("Entry allowed.");
            }
        }
    }
}
```

**Output:**

```text
Entry allowed.
```

**Explanation:**

- The outer condition `age >= 18` is `true`.
- Java enters the outer block and checks `hasID`.
- Since `hasID` is also `true`, the message is printed.

## 4. Example with an Outer Condition That Is False

```java
public class Main {
    public static void main(String[] args) {
        int age = 16;

        if (age >= 18) {
            if (age < 60) {
                System.out.println("Eligible.");
            }
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

The outer condition `age >= 18` is `false`. Therefore, Java skips the entire outer block, including the inner `if` statement.

## 5. Example: Checking a Number

A nested `if` statement can classify a number as positive and then check whether it is even or odd.

```java
public class Main {
    public static void main(String[] args) {
        int number = 8;

        if (number > 0) {
            if (number % 2 == 0) {
                System.out.println("Positive even number.");
            } else {
                System.out.println("Positive odd number.");
            }
        } else {
            System.out.println("The number is not positive.");
        }
    }
}
```

**Output:**

```text
Positive even number.
```

**Explanation:**

1. The outer condition checks whether `number > 0`.
2. Because the number is positive, Java enters the outer block.
3. The inner condition checks whether `number % 2 == 0`.
4. Since the remainder is zero, the program prints `Positive even number.`

## 6. Nested if vs. Logical Operators

Sometimes, nested `if` statements can be replaced with a single `if` statement using a logical operator.

### Using nested if

```java
if (age >= 18) {
    if (hasID) {
        System.out.println("Entry allowed.");
    }
}
```

### Using the logical AND operator

```java
if (age >= 18 && hasID) {
    System.out.println("Entry allowed.");
}
```

Both examples produce the same result for these conditions.

The `&&` operator is useful when both conditions must be true. Nested `if` statements are useful when the second condition or action belongs naturally inside the first decision.

## 7. Important Points

- A nested `if` statement contains another `if` statement inside a conditional block.
- The inner condition is checked only when execution reaches the inner statement.
- If an outer condition is false, its inner statements are skipped.
- Nested `if` statements can be combined with `else` and `else-if`.
- Excessive nesting can make code difficult to read, so simpler conditions should be preferred when appropriate.
- Curly braces and proper indentation help show which statements belong to each condition.

## 8. Conclusion

Nested `if` statements allow Java programs to make decisions that depend on multiple levels of conditions. They are useful when one decision determines whether another decision should be considered.

## 9. Next Topic

Continue learning with the next topic:

[The switch Statement in Java](06-switch-Statement.md)
