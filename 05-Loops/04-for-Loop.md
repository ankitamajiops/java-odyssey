# The `for` Loop in Java

## 1. What Is a `for` Loop?

The `for` loop is a control-flow statement used to execute a block of code repeatedly. It is especially useful when the number of iterations is known or controlled by a counter.

For example, if we want to print the numbers from 1 to 5, a `for` loop lets us write the instructions in a compact form.

## 2. Syntax

```java
for (initialization; condition; update) {
    // Statements to execute
}
```

A `for` loop has three main parts:

- **Initialization:** Runs once before the loop starts.
- **Condition:** Checked before each iteration. If it is `true`, the body executes.
- **Update:** Runs after each iteration of the body.

The loop stops when its condition becomes `false`.

## 3. Simple Example

This program prints the numbers from 1 to 5.

```java
public class Main {
    public static void main(String[] args) {
        for (int i = 1; i <= 5; i++) {
            System.out.println(i);
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

- `int i = 1` initializes the counter.
- `i <= 5` checks whether the counter is at most 5.
- `System.out.println(i)` prints the current value.
- `i++` increases the counter by 1 after each iteration.

When `i` becomes 6, the condition is false, so the loop ends.

## 4. Execution Flow of a `for` Loop

Consider this loop:

```java
for (int i = 1; i <= 3; i++) {
    System.out.println(i);
}
```

Its execution follows this order:

1. Initialize `i` to 1.
2. Check whether `i <= 3`.
3. If true, print `i`.
4. Execute `i++`.
5. Check the condition again.
6. Repeat until the condition becomes false.

| Iteration | Value of `i` | Condition | Output |
|---|---:|---|---|
| 1 | 1 | `true` | 1 |
| 2 | 2 | `true` | 2 |
| 3 | 3 | `true` | 3 |
| Final check | 4 | `false` | No output |

## 5. Print Even Numbers

A `for` loop can print even numbers in a given range.

```java
public class Main {
    public static void main(String[] args) {
        for (int i = 2; i <= 10; i += 2) {
            System.out.println(i);
        }
    }
}
```

Output:

```text
2
4
6
8
10
```

Here, `i += 2` increases the value of `i` by 2 after every iteration.

## 6. Calculate the Sum of the First `n` Natural Numbers

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter n: ");
        int n = sc.nextInt();

        int sum = 0;

        for (int i = 1; i <= n; i++) {
            sum += i;
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

For `n = 5`, the loop performs these additions:

| Iteration | Value of `i` | Value of `sum` |
|---|---:|---:|
| Initial | — | 0 |
| 1 | 1 | 1 |
| 2 | 2 | 3 |
| 3 | 3 | 6 |
| 4 | 4 | 10 |
| 5 | 5 | 15 |

After the fifth iteration, `i` becomes 6. The condition `i <= n` becomes false, and the loop terminates.

If `n` is zero or negative, the loop body executes zero times and the sum remains 0.

## 7. Counting Backward

A `for` loop can count down as well as up.

```java
public class Main {
    public static void main(String[] args) {
        for (int i = 5; i >= 1; i--) {
            System.out.println(i);
        }
    }
}
```

Output:

```text
5
4
3
2
1
```

Here, `i--` decreases the counter by 1 after each iteration.

## 8. Multiple Variables in a `for` Loop

A `for` loop can initialize and update more than one variable.

```java
public class Main {
    public static void main(String[] args) {
        for (int i = 1, j = 5; i <= 5; i++, j--) {
            System.out.println(i + " " + j);
        }
    }
}
```

Output:

```text
1 5
2 4
3 3
4 2
5 1
```

Both variables are updated after each iteration. In this example, `i` increases while `j` decreases.

## 9. Omitting Parts of a `for` Loop

The initialization, condition, and update sections can be omitted when appropriate. The semicolons must remain in place.

### Omitting initialization

```java
int i = 1;

for (; i <= 3; i++) {
    System.out.println(i);
}
```

### Omitting the update section

```java
for (int i = 1; i <= 3;) {
    System.out.println(i);
    i++;
}
```

### Omitting the condition

```java
for (;;) {
    System.out.println("Running");
}
```

When the condition is omitted, it is treated as always true. Therefore, the last example is an infinite loop unless something inside the loop exits it.

## 10. The Scope of the Loop Variable

A variable declared in the initialization section is normally accessible only within that `for` loop.

```java
public class Main {
    public static void main(String[] args) {
        for (int i = 1; i <= 3; i++) {
            System.out.println(i);
        }

        // System.out.println(i); // Compilation error
    }
}
```

The variable `i` cannot be accessed outside the loop because it was declared inside the loop's initialization section.

If a counter needs to be used after the loop, declare it before the loop.

## 11. Common Mistakes

### Using the wrong condition

```java
for (int i = 1; i < 5; i++) {
    System.out.println(i);
}
```

Output:

```text
1
2
3
4
```

The condition `i < 5` excludes 5. Use `i <= 5` if you want to include it.

### Forgetting to update the counter

```java
for (int i = 1; i <= 5;) {
    System.out.println(i);
}
```

This loop does not terminate because `i` never changes. Add an update such as `i++`.

### Adding an unnecessary semicolon

```java
for (int i = 1; i <= 3; i++); {
    System.out.println("Hello");
}
```

The semicolon immediately after the `for` statement creates an empty loop body. The block that follows is separate and executes only once.

The correct version is:

```java
for (int i = 1; i <= 3; i++) {
    System.out.println("Hello");
}
```

Output:

```text
Hello
Hello
Hello
```

## 12. When Should You Use a `for` Loop?

A `for` loop is a good choice when:

- You know how many times an operation should repeat.
- You need to count upward or downward.
- You want to iterate through a numerical range.
- Initialization, condition, and update are naturally connected.

A `while` loop may be clearer when repetition depends on a condition and the number of iterations is not known in advance.

## Conclusion

The `for` loop combines initialization, condition checking, and updating in one structure. Understanding these three parts helps you control repetition, calculate sums, generate sequences, and solve programming problems efficiently.

## Next Topic

Continue with [The Enhanced `for` Loop](05-Enhanced-for-Loop.md).
