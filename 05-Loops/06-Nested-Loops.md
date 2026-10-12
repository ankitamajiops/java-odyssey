# Nested Loops in Java

## 1. What Are Nested Loops?

A nested loop is a loop placed inside another loop.

The loop on the outside is called the **outer loop**, and the loop inside it is called the **inner loop**.

Nested loops are useful for working with patterns, tables, matrices, and problems that require repeated operations across rows and columns.

## 2. Basic Syntax

```java
for (initialization; condition; update) {
    // Outer loop statements

    for (initialization; condition; update) {
        // Inner loop statements
    }
}
```

The inner loop executes completely for each iteration of the outer loop, unless its execution is interrupted.

## 3. Simple Example

```java
public class Main {
    public static void main(String[] args) {
        for (int i = 1; i <= 3; i++) {
            for (int j = 1; j <= 2; j++) {
                System.out.println("i = " + i + ", j = " + j);
            }
        }
    }
}
```

Output:

```text
i = 1, j = 1
i = 1, j = 2
i = 2, j = 1
i = 2, j = 2
i = 3, j = 1
i = 3, j = 2
```

### Explanation

- The outer loop runs three times because `i` takes the values 1, 2, and 3.
- For each value of `i`, the inner loop runs twice because `j` takes the values 1 and 2.
- Therefore, the inner statement executes \(3 \times 2 = 6\) times.

## 4. Understanding the Execution Order

Consider this code:

```java
for (int i = 1; i <= 2; i++) {
    for (int j = 1; j <= 3; j++) {
        System.out.print("* ");
    }

    System.out.println();
}
```

Output:

```text
* * *
* * *
```

The outer loop controls the rows, while the inner loop controls the number of stars in each row.

| Outer loop (`i`) | Inner loop (`j`) values | Stars printed |
|---|---|---:|
| 1 | 1, 2, 3 | 3 |
| 2 | 1, 2, 3 | 3 |

The inner loop starts again from its initialization each time the outer loop begins another iteration.

## 5. Example: Print a Rectangle Pattern

```java
public class Main {
    public static void main(String[] args) {
        int rows = 4;
        int columns = 5;

        for (int i = 1; i <= rows; i++) {
            for (int j = 1; j <= columns; j++) {
                System.out.print("* ");
            }

            System.out.println();
        }
    }
}
```

Output:

```text
* * * * *
* * * * *
* * * * *
* * * * *
```

### Explanation

- `rows = 4` means the outer loop executes four times.
- `columns = 5` means the inner loop prints five stars per row.
- `System.out.println()` moves the cursor to the next line after each row.

The program prints 20 stars in total.

## 6. Example: Print a Right-Angled Triangle

```java
public class Main {
    public static void main(String[] args) {
        int rows = 5;

        for (int i = 1; i <= rows; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print("* ");
            }

            System.out.println();
        }
    }
}
```

Output:

```text
*
* *
* * *
* * * *
* * * * *
```

### Explanation

The inner loop condition is `j <= i`, so the number of stars depends on the current row.

| Row (`i`) | Inner loop values (`j`) | Number of stars |
|---|---|---:|
| 1 | 1 | 1 |
| 2 | 1, 2 | 2 |
| 3 | 1, 2, 3 | 3 |
| 4 | 1, 2, 3, 4 | 4 |
| 5 | 1, 2, 3, 4, 5 | 5 |

This is one of the most common applications of nested loops in beginner programming.

## 7. Example: Multiplication Table

The following program prints multiplication tables from 1 to 3, with each table showing results from 1 to 5.

```java
public class Main {
    public static void main(String[] args) {
        for (int i = 1; i <= 3; i++) {
            System.out.println("Table of " + i);

            for (int j = 1; j <= 5; j++) {
                System.out.println(i + " x " + j + " = " + (i * j));
            }

            System.out.println();
        }
    }
}
```

Output:

```text
Table of 1
1 x 1 = 1
1 x 2 = 2
1 x 3 = 3
1 x 4 = 4
1 x 5 = 5

Table of 2
2 x 1 = 2
2 x 2 = 4
2 x 3 = 6
2 x 4 = 8
2 x 5 = 10

Table of 3
3 x 1 = 3
3 x 2 = 6
3 x 3 = 9
3 x 4 = 12
3 x 5 = 15
```

The outer loop selects the table, and the inner loop generates its multiplication results.

## 8. Nested `while` Loops

Nested loops do not have to use `for` statements. A `while` loop can be placed inside another `while` loop.

```java
public class Main {
    public static void main(String[] args) {
        int i = 1;

        while (i <= 2) {
            int j = 1;

            while (j <= 3) {
                System.out.print(j + " ");
                j++;
            }

            System.out.println();
            i++;
        }
    }
}
```

Output:

```text
1 2 3
1 2 3
```

Notice that `j` is initialized inside the outer loop. This allows the inner loop to start from 1 each time the outer loop repeats.

## 9. How Many Times Does a Nested Loop Execute?

If an outer loop executes \(m\) times and an inner loop executes \(n\) times for every outer iteration, the inner body executes \(m \times n\) times.

For example:

```java
for (int i = 1; i <= 4; i++) {
    for (int j = 1; j <= 3; j++) {
        System.out.println("Hello");
    }
}
```

The outer loop executes 4 times, and the inner loop executes 3 times per outer iteration.

Total executions:

\[
4 \times 3 = 12
\]

Therefore, `Hello` is printed 12 times.

This multiplication rule assumes the inner loop runs the same number of times for every outer iteration. If the inner loop's limit depends on the outer variable, count the iterations separately.

## 10. Common Mistakes

### Forgetting to reset the inner loop variable

Incorrect:

```java
int j = 1;

for (int i = 1; i <= 3; i++) {
    while (j <= 2) {
        System.out.println(i + " " + j);
        j++;
    }
}
```

The inner loop runs during the first outer iteration only. Afterward, `j` is 3, so `j <= 2` is false for every remaining iteration.

Correct:

```java
for (int i = 1; i <= 3; i++) {
    for (int j = 1; j <= 2; j++) {
        System.out.println(i + " " + j);
    }
}
```

The inner loop variable is initialized again for each outer iteration.

### Placing `println()` in the wrong location

If `System.out.println()` is inside the inner loop, every item appears on a separate line. If it comes after the inner loop, it moves to the next line after the row is complete.

### Using unnecessary nesting

If a task can be completed with a single loop, adding another loop may make the program harder to understand and less efficient.

## 11. When Should You Use Nested Loops?

Nested loops are useful when:

- Printing star and number patterns.
- Generating multiplication tables.
- Processing rows and columns of a two-dimensional array.
- Comparing elements from two sequences.
- Performing operations that involve pairs of values.

Keep in mind that nested loops can increase execution time significantly when the number of iterations becomes large.

## Conclusion

Nested loops allow one loop to repeat another loop. The outer loop often controls rows or groups, while the inner loop controls work within each group. Understanding their execution order is essential for solving pattern-printing, matrix, and other programming problems.

## Next Topic

Continue with [The `break` Statement](07-break-Statement.md).
