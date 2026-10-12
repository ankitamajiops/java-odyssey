# The `break` Statement in Java

## 1. What Is the `break` Statement?

The `break` statement is used to terminate a loop or a `switch` statement immediately.

When Java encounters `break` inside a loop, it exits the nearest enclosing loop and continues executing the statement immediately after that loop.

It is useful when a program has completed its task and no further iterations are necessary.

## 2. Syntax

```java
break;
```

The `break` statement does not require a condition. It is usually placed inside an `if` statement when a particular condition determines when the loop should stop.

## 3. Example: Stop a Loop Early

```java
public class Main {
    public static void main(String[] args) {
        for (int i = 1; i <= 10; i++) {
            if (i == 5) {
                break;
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
3
4
```

### Explanation

1. The loop starts with `i = 1`.
2. Java checks whether `i == 5`.
3. When `i` is 1, 2, 3, or 4, the condition is false, so the number is printed.
4. When `i` becomes 5, the condition is true.
5. The `break` statement terminates the loop immediately.

Therefore, 5 and the remaining numbers are not printed.

## 4. Example: Search for an Element in an Array

The `break` statement is useful when searching for an element because the search can stop as soon as the target is found.

```java
public class Main {
    public static void main(String[] args) {
        int[] numbers = {10, 25, 30, 45, 50};
        int target = 30;
        boolean found = false;

        for (int number : numbers) {
            if (number == target) {
                found = true;
                break;
            }
        }

        if (found) {
            System.out.println("Element found");
        } else {
            System.out.println("Element not found");
        }
    }
}
```

Output:

```text
Element found
```

### Explanation

- The loop examines each array element.
- When `number` becomes 30, the condition `number == target` is true.
- The variable `found` becomes `true`.
- The `break` statement stops the search because the target has been found.
- The final `if-else` statement prints the result.

If the target is absent, the loop finishes normally and `found` remains `false`.

## 5. Example: Find the First Number Divisible by 7

```java
public class Main {
    public static void main(String[] args) {
        for (int i = 1; i <= 50; i++) {
            if (i % 7 == 0) {
                System.out.println("First number divisible by 7: " + i);
                break;
            }
        }
    }
}
```

Output:

```text
First number divisible by 7: 7
```

The loop checks numbers in increasing order. Once it reaches 7, the condition `i % 7 == 0` is true, and `break` stops further checking.

## 6. The `break` Statement in Nested Loops

When `break` is used inside a nested loop, it terminates only the **nearest enclosing loop**.

```java
public class Main {
    public static void main(String[] args) {
        for (int i = 1; i <= 3; i++) {
            for (int j = 1; j <= 3; j++) {
                if (j == 2) {
                    break;
                }

                System.out.println("i = " + i + ", j = " + j);
            }
        }
    }
}
```

Output:

```text
i = 1, j = 1
i = 2, j = 1
i = 3, j = 1
```

### Explanation

For every outer-loop iteration:

1. The inner loop begins with `j = 1`.
2. The program prints the current values.
3. When `j` becomes 2, the `break` statement exits the inner loop.
4. The outer loop continues with the next value of `i`.

The outer loop does not terminate because the `break` statement belongs to the inner loop.

## 7. Using `break` with a `while` Loop

The `break` statement works with `while` and `do-while` loops as well.

```java
public class Main {
    public static void main(String[] args) {
        int i = 1;

        while (i <= 10) {
            if (i == 4) {
                break;
            }

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
```

When `i` reaches 4, the loop terminates before printing that value.

## 8. Using `break` in a `switch` Statement

In a traditional `switch` statement, `break` can prevent execution from continuing into the next case.

```java
public class Main {
    public static void main(String[] args) {
        int day = 2;

        switch (day) {
            case 1:
                System.out.println("Monday");
                break;
            case 2:
                System.out.println("Tuesday");
                break;
            default:
                System.out.println("Other day");
        }
    }
}
```

Output:

```text
Tuesday
```

Here, `break` exits the `switch` after the matching case executes.

Traditional `switch` statements can sometimes intentionally use fall-through. However, when that behavior is not intended, `break` helps prevent it.

## 9. Labeled `break`

Java also supports a labeled `break`, which can terminate a specific enclosing loop rather than only the nearest one.

```java
public class Main {
    public static void main(String[] args) {
        outer:
        for (int i = 1; i <= 3; i++) {
            for (int j = 1; j <= 3; j++) {
                if (i == 2 && j == 2) {
                    break outer;
                }

                System.out.println(i + " " + j);
            }
        }

        System.out.println("Loops ended");
    }
}
```

Output:

```text
1 1
1 2
1 3
2 1
Loops ended
```

### Explanation

- `outer:` labels the outer loop.
- When `i == 2` and `j == 2`, `break outer;` terminates the labeled outer loop.
- Both loops stop, and execution continues after the labeled loop.

Labeled `break` is useful in some nested-loop situations, but ordinary `break` is usually easier to read.

## 10. `break` vs. Normal Loop Termination

| Feature | `break` | Normal termination |
|---|---|---|
| How it happens | Immediately exits the loop when executed | The loop condition becomes false |
| Remaining iterations | Skipped | No further iterations occur |
| Typical use | Stop when a target or special condition is reached | Complete all iterations allowed by the condition |

## 11. Common Mistakes

### Using `break` outside a loop or `switch`

An ordinary `break` cannot be used anywhere in a method. It must appear in an appropriate enclosing loop or `switch` statement, except for valid labeled-break contexts.

### Assuming `break` exits every nested loop

An unlabeled `break` exits only the nearest enclosing loop or `switch`. Use a labeled `break` when you need to exit a particular enclosing loop.

### Placing `break` before required work

Statements after `break` in the same execution path are skipped. Make sure any required processing happens before the loop exits.

## Conclusion

The `break` statement terminates the nearest enclosing loop or `switch` immediately. It is useful for searching, stopping repetitive work early, and preventing unnecessary iterations. In nested loops, remember that an ordinary `break` exits only the innermost applicable structure.

## Next Topic

Continue with [The `continue` Statement](08-continue-Statement.md).
