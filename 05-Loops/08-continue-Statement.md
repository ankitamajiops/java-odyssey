# The `continue` Statement in Java

## 1. What Is the `continue` Statement?

The `continue` statement skips the remaining statements in the current loop iteration and moves on to the next iteration.

Unlike `break`, which terminates a loop, `continue` allows the loop to keep running.

It is useful when you want to skip certain values or ignore specific cases without stopping the entire loop.

## 2. Syntax

```java
continue;
```

The `continue` statement is generally used inside a loop, often with an `if` condition.

## 3. Example: Skip a Number

The following program prints numbers from 1 to 5, except 3.

```java
public class Main {
    public static void main(String[] args) {
        for (int i = 1; i <= 5; i++) {
            if (i == 3) {
                continue;
            }

            System.out.println(i);
        }
    }
}
```

Output:

```text
1
2
4
5
```

### Explanation

1. The loop starts with `i = 1`.
2. When `i` is 1 or 2, the condition `i == 3` is false, so the value is printed.
3. When `i` becomes 3, `continue` skips the `System.out.println(i)` statement.
4. The loop proceeds to the next iteration.
5. The values 4 and 5 are printed normally.

Therefore, 3 is skipped, but the loop continues.

## 4. Example: Print Only Even Numbers

The `continue` statement can skip odd numbers.

```java
public class Main {
    public static void main(String[] args) {
        for (int i = 1; i <= 10; i++) {
            if (i % 2 != 0) {
                continue;
            }

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

### Explanation

- The expression `i % 2` gives the remainder after dividing `i` by 2.
- If `i % 2 != 0`, the number is odd.
- `continue` skips the rest of that iteration.
- Only even numbers reach the print statement.

## 5. Using `continue` with a `while` Loop

In a `while` loop, `continue` skips the remaining body and moves to the next condition check.

Be careful to update the loop variable before continuing if the update is otherwise placed later in the body.

**Incorrect example:**

```java
int i = 0;

while (i < 5) {
    if (i == 2) {
        continue;
    }

    System.out.println(i);
    i++;
}
```

This loop becomes stuck when `i` reaches 2. The `continue` statement skips `i++`, so `i` remains 2 and the condition stays true.

**Corrected example:**

```java
public class Main {
    public static void main(String[] args) {
        int i = 0;

        while (i < 5) {
            i++;

            if (i == 3) {
                continue;
            }

            System.out.println(i);
        }
    }
}
```

Output:

```text
1
2
4
5
```

Here, `i` is updated before the condition that may execute `continue`, so the loop continues to make progress.

## 6. Using `continue` with a `do-while` Loop

The `continue` statement also works with a `do-while` loop. After it skips the remaining body, Java evaluates the loop condition.

```java
public class Main {
    public static void main(String[] args) {
        int i = 0;

        do {
            i++;

            if (i == 3) {
                continue;
            }

            System.out.println(i);
        } while (i < 5);
    }
}
```

Output:

```text
1
2
4
5
```

When `i` is 3, the print statement is skipped. Java then checks `i < 5` and continues the loop because the condition is true.

## 7. Using `continue` in Nested Loops

An ordinary `continue` affects only the nearest enclosing loop.

```java
public class Main {
    public static void main(String[] args) {
        for (int i = 1; i <= 3; i++) {
            for (int j = 1; j <= 3; j++) {
                if (j == 2) {
                    continue;
                }

                System.out.println(i + " " + j);
            }
        }
    }
}
```

Output:

```text
1 1
1 3
2 1
2 3
3 1
3 3
```

For each outer-loop iteration, the inner loop skips the case where `j` is 2. The outer loop continues normally.

## 8. Labeled `continue`

Java supports a labeled `continue`, which skips to the next iteration of a specific enclosing loop.

```java
public class Main {
    public static void main(String[] args) {
        outer:
        for (int i = 1; i <= 3; i++) {
            for (int j = 1; j <= 3; j++) {
                if (j == 2) {
                    continue outer;
                }

                System.out.println(i + " " + j);
            }
        }
    }
}
```

Output:

```text
1 1
2 1
3 1
```

### Explanation

- `outer:` labels the outer loop.
- When `j` becomes 2, `continue outer;` skips the rest of the current outer-loop iteration.
- Execution proceeds with the next value of `i`.
- The inner loop does not continue to `j = 3` for that outer iteration.

Labeled `continue` is useful in some nested-loop situations, but ordinary `continue` is usually easier to understand.

## 9. Difference Between `break` and `continue`

| Feature | `break` | `continue` |
|---|---|---|
| Purpose | Terminates the loop | Skips the current iteration |
| Does the loop continue? | No, unless an outer loop continues | Yes, if its condition allows |
| Remaining statements in the current iteration | Skipped | Skipped |
| Common use | Stop searching after finding a result | Skip unwanted values |

### Example using `break`

```java
for (int i = 1; i <= 5; i++) {
    if (i == 3) {
        break;
    }

    System.out.println(i);
}
```

Output:

```text
1
2
```

### Example using `continue`

```java
for (int i = 1; i <= 5; i++) {
    if (i == 3) {
        continue;
    }

    System.out.println(i);
}
```

Output:

```text
1
2
4
5
```

The first program stops at 3, whereas the second skips 3 and continues.

## 10. Common Mistakes

### Forgetting to update a `while` loop variable

If `continue` skips the statement that updates the loop variable, the loop may never terminate.

### Assuming `continue` exits the loop

`continue` does not end the entire loop. It skips the remainder of the current iteration.

### Using `continue` unnecessarily

Sometimes a simple `if` statement makes the code clearer. Use `continue` when it improves readability rather than adding unnecessary control flow.

## Conclusion

The `continue` statement skips the rest of the current iteration and moves to the next one. It is useful for filtering values and skipping unwanted cases. Remember that it behaves differently in `for`, `while`, and `do-while` loops because their update and condition checks occur at different points.

## Next Topic

Continue with [Infinite Loops](09-Infinite-Loops.md).
