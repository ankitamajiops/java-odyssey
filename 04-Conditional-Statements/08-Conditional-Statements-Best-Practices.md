# Conditional Statements: Best Practices in Java

Conditional statements help a program make decisions. Writing them clearly makes code easier to understand, maintain, and debug.

This guide covers practical ways to write readable and reliable conditional statements in Java.

## 1. Always Use Braces

Use curly braces `{}` with `if`, `else`, and loop bodies, even when there is only one statement.

**Less readable:**

```java
int age = 20;

if (age >= 18)
    System.out.println("Eligible");
```

**Recommended:**

```java
int age = 20;

if (age >= 18) {
    System.out.println("Eligible");
}
```

Output:

```text
Eligible
```

Braces make the program structure clear and reduce the chance of mistakes when adding more statements later.

## 2. Keep Conditions Simple and Readable

Write conditions that are easy to understand. Use meaningful variable names and avoid unnecessarily complicated expressions.

**Less readable:**

```java
int a = 20;

if (a > 0 && a < 100 && a != 50) {
    System.out.println("Valid");
}
```

**More readable:**

```java
int score = 20;

boolean isInRange = score > 0 && score < 100;
boolean isNotExcluded = score != 50;

if (isInRange && isNotExcluded) {
    System.out.println("Valid");
}
```

Output:

```text
Valid
```

For simple conditions, however, introducing extra variables may make the code longer than necessary. Choose the clearest approach for the situation.

## 3. Avoid Unnecessary Nested `if` Statements

Deeply nested conditions can make code difficult to follow. When possible, combine related conditions or handle invalid cases early.

**Example:**

```java
int age = 20;
boolean hasID = true;

if (age >= 18 && hasID) {
    System.out.println("Entry allowed");
} else {
    System.out.println("Entry denied");
}
```

Output:

```text
Entry allowed
```

This is easier to read than placing one `if` statement inside another when both conditions must be true.

Nested conditions are still useful when the second decision should be checked only after the first condition succeeds.

## 4. Choose the Appropriate Conditional Statement

Different situations call for different statements.

- Use `if` when a decision depends on a condition.
- Use `if-else` when there are two alternative paths.
- Use an `else-if` ladder when several conditions need to be checked in order.
- Use `switch` when comparing one expression against several fixed alternatives.
- Use a `switch` expression when you want to produce a value from different cases and your Java version supports it.
- Use the ternary operator for short, simple choices.

For example, an `if-else` statement is suitable for checking whether a number is positive:

```java
int number = 7;

if (number > 0) {
    System.out.println("Positive");
} else {
    System.out.println("Zero or negative");
}
```

Output:

```text
Positive
```

## 5. Arrange `else-if` Conditions Carefully

In an `else-if` ladder, Java checks conditions from top to bottom. Once a condition is true, the remaining branches are skipped.

When checking ranges, place more specific or higher-priority conditions appropriately.

**Example:**

```java
int marks = 85;

if (marks >= 90) {
    System.out.println("Grade A");
} else if (marks >= 80) {
    System.out.println("Grade B");
} else if (marks >= 70) {
    System.out.println("Grade C");
} else {
    System.out.println("Needs improvement");
}
```

Output:

```text
Grade B
```

If the condition `marks >= 70` were placed first, a score of `85` would match it, and Java would never reach the higher-grade conditions.

## 6. Include a `default` Case in `switch`

A `default` case provides a fallback when no case matches.

```java
int day = 8;

switch (day) {
    case 1:
        System.out.println("Monday");
        break;
    case 2:
        System.out.println("Tuesday");
        break;
    default:
        System.out.println("Invalid day");
}
```

Output:

```text
Invalid day
```

A `default` case is particularly useful when unexpected or invalid values are possible.

## 7. Understand `switch` Fall-Through

In a traditional `switch` statement, omitting `break` can cause execution to continue into later cases. This is called *fall-through*.

```java
int number = 1;

switch (number) {
    case 1:
        System.out.println("One");
        break;
    case 2:
        System.out.println("Two");
        break;
    default:
        System.out.println("Other");
}
```

Output:

```text
One
```

Use `break` when you want to stop after a matching case. Intentional fall-through is possible, but it should be clear from the code.

## 8. Use the Ternary Operator Only for Simple Choices

The ternary operator is a concise alternative to a basic `if-else` expression.

```java
int age = 20;

String result = age >= 18 ? "Adult" : "Minor";

System.out.println(result);
```

Output:

```text
Adult
```

Avoid chaining many ternary operators together. For complicated decisions, a regular `if-else` structure is generally easier to understand.

## 9. Avoid Unnecessary Boolean Comparisons

When a condition already evaluates to a boolean, you usually do not need to compare it with `true` or `false`.

**Unnecessary:**

```java
boolean isLoggedIn = true;

if (isLoggedIn == true) {
    System.out.println("Welcome");
}
```

**Simpler:**

```java
boolean isLoggedIn = true;

if (isLoggedIn) {
    System.out.println("Welcome");
}
```

Output:

```text
Welcome
```

To check whether a boolean value is false, use the logical NOT operator `!`:

```java
if (!isLoggedIn) {
    System.out.println("Please log in");
}
```

## 10. Check Boundary Values

When checking ranges, carefully consider the boundary values and choose the correct comparison operators.

For example, if a person must be at least 18 years old, use `age >= 18`, not `age > 18`.

```java
int age = 18;

if (age >= 18) {
    System.out.println("Eligible");
} else {
    System.out.println("Not eligible");
}
```

Output:

```text
Eligible
```

Also consider values at the lower and upper ends of a range, including zero and negative numbers when they are possible.

## 11. Use Modern `switch` Expressions When Appropriate

In Java versions that support switch expressions, you can return a value directly from a `switch`.

```java
int day = 1;

String dayType = switch (day) {
    case 1, 7 -> "Weekend";
    case 2, 3, 4, 5, 6 -> "Weekday";
    default -> "Invalid day";
};

System.out.println(dayType);
```

Output:

```text
Weekend
```

This example uses the simplified weekday numbering where `1` and `7` represent the weekend. Switch expressions became a permanent Java feature in Java 14.

## Conclusion

Good conditional statements should be readable, logically correct, and appropriate for the problem. Use braces, choose the right statement, check boundaries carefully, and avoid unnecessary complexity. Clear conditions make Java programs easier to understand and maintain.

## Next Topic

Continue learning Java with the next section: [Loops in Java](../05-Loops/README.md).
