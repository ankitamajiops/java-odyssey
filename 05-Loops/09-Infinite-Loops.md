# Infinite Loops in Java

## 1. What Is an Infinite Loop?

An **infinite loop** is a loop that continues executing indefinitely because its termination condition never becomes false, or because the loop does not contain a reachable exit condition.

Infinite loops can be created using `while`, `do-while`, and `for` loops.

They are sometimes intentional, such as when a program must continuously wait for user input or monitor a process. However, an unintended infinite loop can prevent a program from progressing normally.

## 2. Infinite `while` Loop

A `while` loop continues as long as its condition evaluates to `true`.

If the condition always remains `true`, the loop does not terminate naturally.

### Example

```java
public class Main {
    public static void main(String[] args) {
        while (true) {
            System.out.println("Java");
        }
    }
}
```

### Output

```text
Java
Java
Java
Java
...
```

The word `Java` continues to print because `true` never becomes `false`.

**Important:** This program will keep printing until it is interrupted or terminated.

## 3. Infinite `for` Loop

A `for` loop can also run indefinitely when its condition is omitted.

### Syntax

```java
for (;;) {
    // Statements
}
```

### Example

```java
public class Main {
    public static void main(String[] args) {
        for (;;) {
            System.out.println("Loop is running");
        }
    }
}
```

### Output

```text
Loop is running
Loop is running
Loop is running
...
```

The three sections inside the parentheses are omitted:

- Initialization
- Condition
- Update

When the condition is omitted, a traditional `for` loop has no condition that can make it terminate naturally.

## 4. Infinite `do-while` Loop

A `do-while` loop can become infinite when its condition always evaluates to `true`.

### Example

```java
public class Main {
    public static void main(String[] args) {
        do {
            System.out.println("Running");
        } while (true);
    }
}
```

### Output

```text
Running
Running
Running
...
```

The loop body executes first, and the condition is checked afterward. Since the condition is always `true`, the loop continues.

## 5. How an Infinite Loop Can Occur Accidentally

An infinite loop can happen even when the programmer does not intend to create one.

Consider this example:

```java
public class Main {
    public static void main(String[] args) {
        int i = 1;

        while (i <= 5) {
            System.out.println(i);
        }
    }
}
```

### What Is Wrong?

The variable `i` starts at `1`, and the condition `i <= 5` is true. However, the value of `i` never changes inside the loop.

Therefore, the condition remains true, and the program repeatedly prints `1`.

### Corrected Code

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

### Output

```text
1
2
3
4
5
```

The statement `i++` increases `i` by one during every iteration. Eventually, `i` becomes `6`, making the condition false and ending the loop.

## 6. How to Stop an Infinite Loop

An infinite loop can be stopped in several ways:

1. **Use a condition that eventually becomes false.** Update the relevant variable correctly.
2. **Use a `break` statement.** Exit the loop when a specific condition is met.
3. **Interrupt the running program.** In a terminal, use `Ctrl + C` when supported. In an IDE, use its Stop button.

### Example Using `break`

```java
public class Main {
    public static void main(String[] args) {
        int i = 1;

        while (true) {
            System.out.println(i);

            if (i == 5) {
                break;
            }

            i++;
        }
    }
}
```

### Output

```text
1
2
3
4
5
```

Although the condition is always `true`, the `break` statement terminates the loop when `i` reaches `5`.

## 7. Best Practices

- Ensure that loop variables are updated when the termination condition depends on them.
- Check that the loop has a clear and reachable exit condition.
- Use infinite loops intentionally, not accidentally.
- Include a suitable exit mechanism when a program needs to run continuously.
- Test loops with small examples before using them in larger programs.

## Next Topic

Continue to [Choosing the Right Loop](10-Choosing-the-Right-Loop.md) to learn when to use `while`, `do-while`, and `for` loops.
