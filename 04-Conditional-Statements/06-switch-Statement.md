# The switch Statement in Java

## 1. Introduction

The `switch` statement in Java is a conditional statement used to select one block of code from several possible alternatives.

It compares an expression with different `case` labels. When a matching case is found, execution begins from that case.

The `switch` statement is often useful when a variable or expression needs to be compared against several specific values.

## 2. Syntax

```java
switch (expression) {
    case value1:
        // Statements
        break;

    case value2:
        // Statements
        break;

    default:
        // Statements executed when no case matches
}
```

**Explanation:**

- `switch`: Begins the selection statement.
- `expression`: The value Java evaluates.
- `case`: Specifies a value to compare with the expression.
- `break`: Exits the switch statement.
- `default`: An optional branch executed when no case matches, provided execution has not fallen through to it from another case.

## 3. Basic Example

```java
public class Main {
    public static void main(String[] args) {
        int day = 3;

        switch (day) {
            case 1:
                System.out.println("Monday");
                break;

            case 2:
                System.out.println("Tuesday");
                break;

            case 3:
                System.out.println("Wednesday");
                break;

            default:
                System.out.println("Invalid day");
        }
    }
}
```

**Output:**

```text
Wednesday
```

**Explanation:**

1. The variable `day` contains `3`.
2. Java finds the matching `case 3`.
3. It prints `Wednesday`.
4. The `break` statement exits the switch.

## 4. The Purpose of break

The `break` statement stops execution within the switch statement and transfers control to the statement following it.

Without `break`, execution can continue into subsequent case bodies. This behavior is called **fall-through**.

### Example Without break

```java
public class Main {
    public static void main(String[] args) {
        int number = 1;

        switch (number) {
            case 1:
                System.out.println("One");

            case 2:
                System.out.println("Two");

            default:
                System.out.println("Other");
        }
    }
}
```

**Output:**

```text
One
Two
Other
```

**Explanation:**

The matching `case 1` executes first. Because there are no `break` statements, Java continues into `case 2` and then `default`.

Use fall-through intentionally; otherwise, include `break` in traditional switch statements to avoid unexpected results.

## 5. The default Case

The `default` branch handles values that do not match any case label.

```java
public class Main {
    public static void main(String[] args) {
        int choice = 5;

        switch (choice) {
            case 1:
                System.out.println("Start");
                break;

            case 2:
                System.out.println("Settings");
                break;

            default:
                System.out.println("Invalid choice");
        }
    }
}
```

**Output:**

```text
Invalid choice
```

The value `5` matches neither `case 1` nor `case 2`, so the `default` branch executes.

## 6. switch with String

Java also supports `String` expressions in switch statements.

```java
public class Main {
    public static void main(String[] args) {
        String language = "Java";

        switch (language) {
            case "Java":
                System.out.println("Object-oriented programming");
                break;

            case "Python":
                System.out.println("Readable syntax");
                break;

            default:
                System.out.println("Other language");
        }
    }
}
```

**Output:**

```text
Object-oriented programming
```

The switch expression matches `"Java"`, so the corresponding case executes.

## 7. Multiple Cases for the Same Action

Several case labels can share the same block of code.

```java
public class Main {
    public static void main(String[] args) {
        int day = 6;

        switch (day) {
            case 6:
            case 7:
                System.out.println("Weekend");
                break;

            default:
                System.out.println("Weekday");
        }
    }
}
```

**Output:**

```text
Weekend
```

Both `case 6` and `case 7` lead to the same statements. This is useful when multiple values require the same action.

## 8. Types Supported by switch

Traditional Java switch statements support certain types, including:

- `byte`, `short`, `char`, and `int`, along with compatible constant values.
- Their corresponding wrapper types, such as `Integer` and `Character`.
- `String`.
- Enum types.

The `long`, `float`, `double`, and `boolean` types are not directly supported as traditional switch selector types.

Modern Java versions also support additional switch features, including pattern matching, depending on the Java version.

## 9. switch vs. if-else

| switch | if-else |
|---|---|
| Useful for selecting among specific case values. | Useful for evaluating a wide variety of boolean conditions. |
| Can match a value against case labels. | Can check ranges and combine conditions. |
| Traditional statements may use `break` to prevent fall-through. | Does not have switch-style fall-through. |
| Can be clear when many alternatives share one expression. | Often better for complex conditions or ranges. |

## 10. Important Points

- A switch statement selects a branch based on its expression and case labels.
- `case` labels specify the alternatives.
- `break` exits a traditional switch statement.
- Without `break`, execution can fall through into later case bodies.
- The `default` branch is optional.
- Multiple case labels can share a block.
- The supported features depend on the Java version being used.

## 11. Conclusion

The `switch` statement is useful when a program needs to choose among several specific alternatives. Understanding case labels, `break`, `default`, and fall-through helps you write clear and correct Java code.

## 12. Next Topic

Continue learning with the next topic:

[The Modern switch Expression in Java](07-Switch-Expression.md)
