# Introduction to Loops in Java

## 1. What Is a Loop?

A loop is a control-flow statement that executes a block of code repeatedly while a condition is satisfied or for a specified number of iterations.

Without loops, we may need to write the same statement many times.

For example, to print a message five times without a loop:

```java
System.out.println("Hello");
System.out.println("Hello");
System.out.println("Hello");
System.out.println("Hello");
System.out.println("Hello");
```

Using a loop makes the code shorter and easier to maintain.

```java
for (int i = 1; i <= 5; i++) {
    System.out.println("Hello");
}
```

Output:

```text
Hello
Hello
Hello
Hello
Hello
```

Both programs print the message five times, but the loop avoids repeating the same statement.

## 2. Why Do We Need Loops?

Loops are useful when a task needs to be repeated.

Common examples include:

- Printing a sequence of numbers.
- Calculating the sum of numbers.
- Processing array elements.
- Repeating a task until the user enters valid input.
- Generating multiplication tables and patterns.
- Searching for an element in a collection.

## 3. Types of Loops in Java

Java provides three basic loop statements:

| Loop | Description |
|---|---|
| `while` | Checks the condition before each iteration. |
| `do-while` | Executes the body before checking the condition. |
| `for` | Combines initialization, condition, and update in one statement. |

Java also provides the enhanced `for` loop, which is useful for iterating through arrays and other iterable data.

## 4. Basic Structure of a Loop

Most loops involve three important parts:

1. **Initialization:** Sets the starting value of a control variable, when needed.
2. **Condition:** Determines whether another iteration should occur.
3. **Update:** Changes the control variable so the loop can eventually finish, when needed.

Consider this example:

```java
for (int i = 1; i <= 3; i++) {
    System.out.println(i);
}
```

Output:

```text
1
2
3
```

Here:

- `int i = 1` initializes the variable.
- `i <= 3` is the condition.
- `i++` increases `i` by one after each iteration.
- `System.out.println(i)` prints the current value.

## 5. How Does a Loop Execute?

The loop above works as follows:

| Iteration | Value of `i` | Condition `i <= 3` | Action |
|---|---:|---|---|
| 1 | 1 | True | Print `1` |
| 2 | 2 | True | Print `2` |
| 3 | 3 | True | Print `3` |
| Check after iteration 3 | 4 | False | Stop the loop |

When `i` becomes `4`, the condition is false, so the loop terminates.

## 6. Entry-Controlled and Exit-Controlled Loops

Loops can also be classified according to when their conditions are checked.

### Entry-controlled loops

The condition is checked before the body executes.

Examples:
- `while`
- `for`

If the condition is false initially, the body may execute zero times.

### Exit-controlled loop

The condition is checked after the body executes.

Example:
- `do-while`

The body executes at least once, even if the condition is initially false.

## 7. Example: Calculate the Sum of the First Five Natural Numbers

```java
public class Main {
    public static void main(String[] args) {
        int sum = 0;

        for (int i = 1; i <= 5; i++) {
            sum += i;
        }

        System.out.println("Sum = " + sum);
    }
}
```

Output:

```text
Sum = 15
```

The loop adds `1 + 2 + 3 + 4 + 5`. The variable `sum` stores the running total.

## 8. Important Points to Remember

- A loop repeats a block of code.
- The condition determines whether a loop continues.
- The loop variable should be updated correctly when the loop depends on it.
- A condition that never becomes false can cause an infinite loop.
- Choose the loop structure that makes the program easiest to understand.

## Next Topic

Continue with [The `while` Loop](02-while-Loop.md).
