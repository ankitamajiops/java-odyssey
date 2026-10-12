# The `while` Loop in Java

## 1. What Is a `while` Loop?

The `while` loop is a control-flow statement that repeatedly executes a block of code as long as a specified condition is `true`.

It is useful when we want to repeat an operation but may not know in advance how many iterations will be needed.

### Syntax

```java
while (condition) {
    // Statements to execute
}
```

- **Condition:** Evaluated before each iteration.
- **Loop body:** Executes when the condition is `true`.
- When the condition becomes `false`, the loop terminates.

## 2. Simple Example

The following program prints the numbers from 1 to 5.

```java
public class Main {
    public static void main(String[] args) {
        int i = 1;

        while (i <= 5) {
            System.out.println(i);
            i++;
        }
    }
}
```

Output:

```text
1
2
3
4
5
```

### Explanation

1. `int i = 1;` initializes the loop variable.
2. `while (i <= 5)` checks whether `i` is at most 5.
3. `System.out.println(i);` prints the current value.
4. `i++;` increases `i` by 1.
5. The condition is checked again.
6. When `i` becomes 6, the condition is false and the loop stops.

## 3. How the Loop Executes

For the previous example:

| Iteration | `i` | Condition `i <= 5` | Action |
|---|---:|---|---|
| 1 | 1 | `true` | Print 1 |
| 2 | 2 | `true` | Print 2 |
| 3 | 3 | `true` | Print 3 |
| 4 | 4 | `true` | Print 4 |
| 5 | 5 | `true` | Print 5 |
| Final check | 6 | `false` | Stop |

The update `i++` is essential in this example because it moves the variable toward the point where the condition becomes false.

## 4. Example: Sum of the First `n` Natural Numbers

This program calculates the sum of the first `n` natural numbers using a `while` loop.

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter n: ");
        int n = sc.nextInt();

        int i = 1;
        int sum = 0;

        while (i <= n) {
            sum += i;
            i++;
        }

        System.out.println("Sum = " + sum);

        sc.close();
    }
}
```

Example input:

```text
Enter n: 5
```

Output:

```text
Sum = 15
```

### Explanation

For `n = 5`, the loop adds the numbers from 1 through 5:

- Initially, `sum = 0`.
- Add 1: `sum = 1`.
- Add 2: `sum = 3`.
- Add 3: `sum = 6`.
- Add 4: `sum = 10`.
- Add 5: `sum = 15`.

When `i` becomes 6, the condition `i <= n` is false, so the loop ends.

## 5. A `while` Loop That Executes Zero Times

Because the condition is checked before the loop body, the body may never execute.

```java
public class Main {
    public static void main(String[] args) {
        int i = 10;

        while (i < 5) {
            System.out.println(i);
            i++;
        }

        System.out.println("Loop finished");
    }
}
```

Output:

```text
Loop finished
```

The initial condition `10 < 5` is false, so Java skips the loop body entirely.

## 6. Infinite `while` Loops

An infinite loop continues indefinitely because its condition never becomes false, or because no statement exits the loop.

Example:

```java
while (true) {
    System.out.println("Running");
}
```

This program keeps printing `Running` until it is interrupted.

An accidental infinite loop can occur when the control variable is not updated correctly.

**Incorrect example:**

```java
int i = 1;

while (i <= 5) {
    System.out.println(i);
}
```

Here, `i` never changes, so the condition remains true.

**Corrected example:**

```java
int i = 1;

while (i <= 5) {
    System.out.println(i);
    i++;
}
```

## 7. When Should You Use a `while` Loop?

A `while` loop is especially useful when:

- The number of repetitions is not known beforehand.
- Repetition depends on a condition.
- A program must continue until a particular event occurs.
- Input must be processed until a stopping condition is met.

For a task that clearly requires a fixed number of repetitions, a `for` loop may be more convenient.

## 8. Important Points

- The `while` loop checks its condition before executing the body.
- The condition must evaluate to a boolean value.
- The body can execute zero or more times.
- Update the control variable when necessary to avoid accidental infinite loops.
- If the condition is initially false, the loop body is skipped.

## Next Topic

Continue with [The `do-while` Loop](03-do-while-Loop.md).
