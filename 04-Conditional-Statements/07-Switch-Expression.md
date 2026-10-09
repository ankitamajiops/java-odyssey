# The switch Expression in Java

## 1. Introduction

The switch expression is a modern form of `switch` introduced as a permanent feature in Java 14.

Unlike a traditional switch statement, a switch expression **produces a value** that can be assigned to a variable, returned from a method, or used in another expression.

It provides a concise and readable way to select a result from multiple alternatives.

## 2. Traditional switch Statement vs. switch Expression

A traditional switch statement often uses `case`, `break`, and variable assignments to select a result.

A switch expression can return the selected value directly.

### Traditional switch Statement

```java
public class Main {
    public static void main(String[] args) {
        int day = 2;
        String result;

        switch (day) {
            case 1:
                result = "Monday";
                break;
            case 2:
                result = "Tuesday";
                break;
            default:
                result = "Invalid day";
        }

        System.out.println(result);
    }
}
```

**Output:**

```text
Tuesday
```

### switch Expression

```java
public class Main {
    public static void main(String[] args) {
        int day = 2;

        String result = switch (day) {
            case 1 -> "Monday";
            case 2 -> "Tuesday";
            default -> "Invalid day";
        };

        System.out.println(result);
    }
}
```

**Output:**

```text
Tuesday
```

The switch expression selects a value, which is stored directly in `result`.

## 3. Arrow Labels (`->`)

Modern switch expressions can use arrow labels to associate a case with its result.

### Syntax

```java
String result = switch (expression) {
    case value1 -> result1;
    case value2 -> result2;
    default -> defaultResult;
};
```

**Important points:**

- The arrow operator `->` separates a case label from its result or statement.
- A matching arrow case does not fall through into the next case.
- A switch expression must produce a value for every possible input.
- The `default` branch handles values not covered by other cases, unless the compiler can establish that the cases are exhaustive, such as with an enum.

## 4. Example: Day of the Week

```java
public class Main {
    public static void main(String[] args) {
        int day = 5;

        String dayName = switch (day) {
            case 1 -> "Monday";
            case 2 -> "Tuesday";
            case 3 -> "Wednesday";
            case 4 -> "Thursday";
            case 5 -> "Friday";
            case 6 -> "Saturday";
            case 7 -> "Sunday";
            default -> "Invalid day";
        };

        System.out.println(dayName);
    }
}
```

**Output:**

```text
Friday
```

Since `day` is `5`, the switch expression produces `"Friday"`.

## 5. Multiple Case Labels

Several case labels can share the same result by separating them with commas.

```java
public class Main {
    public static void main(String[] args) {
        int day = 7;

        String type = switch (day) {
            case 1, 2, 3, 4, 5 -> "Weekday";
            case 6, 7 -> "Weekend";
            default -> "Invalid day";
        };

        System.out.println(type);
    }
}
```

**Output:**

```text
Weekend
```

This approach avoids repeating the same result for multiple cases.

## 6. Using a Block with yield

Sometimes a switch expression needs multiple statements before producing a result. In that situation, a block can be used with the `yield` keyword.

### Example

```java
public class Main {
    public static void main(String[] args) {
        int number = 4;

        String result = switch (number) {
            case 1, 2, 3 -> "Small";
            case 4, 5, 6 -> {
                System.out.println("Number is in the middle range.");
                yield "Medium";
            }
            default -> "Other";
        };

        System.out.println(result);
    }
}
```

**Output:**

```text
Number is in the middle range.
Medium
```

**Explanation:**

- The `case 4, 5, 6` block executes.
- The first statement prints a message.
- `yield "Medium"` supplies the value of the switch expression.
- The value is stored in `result`.

The `yield` keyword is used to return a value from a switch-expression block. It is not the same as the `return` statement used to return from a method.

## 7. Supported Java Versions

- Switch expressions became a permanent Java feature in **Java 14**.
- They are not supported by older Java versions that predate their introduction.
- If your compiler reports an error for this syntax, check the installed Java version and the project's language level.

## 8. Important Points

- A switch expression produces a value.
- It can be assigned directly to a variable.
- Arrow labels (`->`) help avoid accidental fall-through.
- Multiple case labels can share one result.
- `yield` supplies a value from a block inside a switch expression.
- A switch expression must be exhaustive, meaning every possible input must be handled.
- Switch expressions are useful when choosing one value from several alternatives.

## 9. Conclusion

The switch expression provides a concise way to select and produce a value based on multiple alternatives. It is a useful modern Java feature that can make decision-making code easier to read and maintain.

## 10. Next Topic

Continue learning with the next topic:

[Conditional Statements Best Practices](08-Conditional-Statements-Best-Practices.md)
