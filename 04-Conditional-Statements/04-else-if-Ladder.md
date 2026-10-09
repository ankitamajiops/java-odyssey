# The else-if Ladder in Java

## 1. Introduction

The `else-if` ladder in Java is used when a program needs to check multiple conditions and choose the appropriate block of code.

Java checks the conditions from top to bottom. The block associated with the **first condition that evaluates to `true`** executes, and the remaining conditions are skipped.

If none of the conditions is true, the optional `else` block executes.

## 2. Syntax

```java
if (condition1) {
    // Executes if condition1 is true
} else if (condition2) {
    // Executes if condition1 is false and condition2 is true
} else if (condition3) {
    // Executes if the earlier conditions are false and condition3 is true
} else {
    // Executes if all conditions are false
}
```

## 3. Basic Example

```java
public class Main {
    public static void main(String[] args) {
        int number = 0;

        if (number > 0) {
            System.out.println("Positive number");
        } else if (number < 0) {
            System.out.println("Negative number");
        } else {
            System.out.println("Zero");
        }
    }
}
```

**Output:**

```text
Zero
```

**Explanation:**

1. Java checks whether `number > 0`. This is false.
2. It checks whether `number < 0`. This is also false.
3. The `else` block executes and prints `Zero`.

## 4. Example: Grading System

An `else-if` ladder can assign a grade based on marks.

```java
public class Main {
    public static void main(String[] args) {
        int marks = 85;

        if (marks >= 90) {
            System.out.println("Grade A");
        } else if (marks >= 80) {
            System.out.println("Grade B");
        } else if (marks >= 70) {
            System.out.println("Grade C");
        } else if (marks >= 60) {
            System.out.println("Grade D");
        } else {
            System.out.println("Grade F");
        }
    }
}
```

**Output:**

```text
Grade B
```

**Explanation:**

- `marks >= 90` is false.
- `marks >= 80` is true.
- Java prints `Grade B` and skips the remaining branches.

The conditions are checked in order, so their arrangement matters.

## 5. Example: Checking a Number's Range

```java
public class Main {
    public static void main(String[] args) {
        int number = 45;

        if (number < 0) {
            System.out.println("Negative");
        } else if (number <= 10) {
            System.out.println("Between 0 and 10");
        } else if (number <= 50) {
            System.out.println("Between 11 and 50");
        } else {
            System.out.println("Greater than 50");
        }
    }
}
```

**Output:**

```text
Between 11 and 50
```

Because the earlier conditions are false and `number <= 50` is true, the third branch executes.

## 6. Important Points

- An `else-if` ladder checks multiple conditions in sequence.
- Conditions are evaluated from top to bottom.
- Only the first matching branch executes.
- The final `else` block is optional.
- If no condition is true and there is no `else` block, no branch executes.
- Condition order matters, especially when ranges overlap.
- Use clear and well-ordered conditions to make the program easier to understand.

## 7. Conclusion

The `else-if` ladder is useful when a program must choose among several alternatives. It is commonly used in grading systems, number classification, and other decision-making tasks.

## 8. Next Topic

Continue learning with the next topic:

[Nested if Statements in Java](05-Nested-if-Statements.md)
