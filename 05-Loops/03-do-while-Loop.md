# The `do-while` Loop in Java

## 1. What Is a `do-while` Loop?

The `do-while` loop is a control-flow statement that executes a block of code at least once before checking a condition.

Unlike a `while` loop, which checks its condition before executing the body, a `do-while` loop checks the condition after executing the body.

This makes it useful when an operation must happen at least once, regardless of whether the condition is initially true or false.

## 2. Syntax

```java
do {
    // Statements to execute
} while (condition);
```

The semicolon (`;`) after the `while` condition is required.

## 3. Simple Example

This program prints the numbers from 1 to 5.

```java
public class Main {
    public static void main(String[] args) {
        int i = 1;

        do {
            System.out.println(i);
            i++;
        } while (i <= 5);
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

1. The variable `i` starts at `1`.
2. Java enters the `do` block and prints `i`.
3. The statement `i++` increases `i` by one.
4. Java checks the condition `i <= 5`.
5. If the condition is `true`, the loop repeats.
6. When `i` becomes `6`, the condition is `false`, so the loop stops.

## 4. The Body Executes at Least Once

This is the most important feature of a `do-while` loop.

```java
public class Main {
    public static void main(String[] args) {
        int i = 10;

        do {
            System.out.println("Value: " + i);
            i++;
        } while (i < 5);
    }
}
```

Output:

```text
Value: 10
```

Although `i < 5` is false, the message is printed once because Java executes the `do` block before checking the condition.

## 5. Difference Between `while` and `do-while`

| Feature | `while` | `do-while` |
|---|---|---|
| Condition checked | Before the body | After the body |
| Minimum executions | Zero | One |
| Semicolon after condition | Not required | Required |
| Common use | Repeat while a condition is true | Execute once, then decide whether to repeat |

### Comparison Example

Using a `while` loop:

```java
int i = 10;

while (i < 5) {
    System.out.println("Hello");
}
```

Output: No output.

Using a `do-while` loop:

```java
int i = 10;

do {
    System.out.println("Hello");
} while (i < 5);
```

Output:

```text
Hello
```

The second program prints `Hello` once even though the condition is initially false.

## 6. Example: Sum of the First `n` Natural Numbers

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter n (at least 1): ");
        int n = sc.nextInt();

        if (n < 1) {
            System.out.println("Please enter a positive integer.");
        } else {
            int i = 1;
            int sum = 0;

            do {
                sum += i;
                i++;
            } while (i <= n);

            System.out.println("Sum = " + sum);
        }

        sc.close();
    }
}
```

Example input:

```text
Enter n (at least 1): 5
```

Output:

```text
Sum = 15
```

### Explanation

For `n = 5`, the loop adds `1 + 2 + 3 + 4 + 5`.

The variable `sum` stores the running total, and `i` moves from `1` to `5`. When `i` becomes `6`, the condition becomes false and the loop ends.

The program checks that `n` is positive before using the loop, because this example is intended to calculate the sum of at least one natural number.

## 7. Example: Repeat an Operation Until a Condition Is Met

A `do-while` loop can be useful when a program needs to display a menu at least once.

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int choice;

        do {
            System.out.println("1. Say Hello");
            System.out.println("0. Exit");
            System.out.print("Enter your choice: ");

            choice = sc.nextInt();

            if (choice == 1) {
                System.out.println("Hello!");
            } else if (choice != 0) {
                System.out.println("Invalid choice");
            }

        } while (choice != 0);

        System.out.println("Program ended.");
        sc.close();
    }
}
```

Example interaction:

```text
1. Say Hello
0. Exit
Enter your choice: 1
Hello!
1. Say Hello
0. Exit
Enter your choice: 0
Program ended.
```

The menu appears at least once. It continues to appear until the user enters `0`.

## 8. Common Mistakes

### Forgetting the semicolon

Incorrect:

```java
do {
    System.out.println("Hello");
} while (false)
```

Correct:

```java
do {
    System.out.println("Hello");
} while (false);
```

### Forgetting to update the loop variable

If the condition remains true and nothing changes it, the loop may continue indefinitely.

```java
int i = 1;

do {
    System.out.println(i);
    i++;
} while (i <= 3);
```

Output:

```text
1
2
3
```

### Using `do-while` when zero executions are needed

If the body should run only when a condition is already true, a `while` loop may be more appropriate.

## 9. When Should You Use a `do-while` Loop?

Use a `do-while` loop when:

- The code must execute at least once.
- A menu should appear before the user chooses an option.
- Input should be requested at least once before validation.
- A task should repeat until a stopping condition is met.

## Conclusion

The `do-while` loop executes its body before checking its condition. Therefore, it always executes at least once. Remember the semicolon after the condition and make sure the loop can eventually terminate.

## Next Topic

Continue with [The `for` Loop](04-for-Loop.md).
