# Return Statement and Return Types in Java

## 1. Introduction

In Java, methods can perform operations and send results back to the code that called them.

Two important concepts are:

- **Return type:** Specifies the type of value a method can return.
- **Return statement:** Transfers a value back to the calling code and ends the current method execution.

Understanding return types and return statements helps us write reusable methods that perform calculations, process data, and provide results.

## 2. What Is a Return Type?

A **return type** is the data type specified in a method declaration that determines the type of value the method can return.

It is written before the method name.

### Syntax

```java
returnType methodName(parameters) {
    // Statements
    return value;
}
```

### Example

```java
public class Main {

    static int getNumber() {
        return 100;
    }

    public static void main(String[] args) {
        int result = getNumber();

        System.out.println(result);
    }
}
```

### Output

```text
100
```

Here:

- `int` is the return type.
- `getNumber()` is the method name.
- `return 100;` returns an integer value.
- The returned value is stored in the `result` variable.

## 3. What Is the Return Statement?

The `return` statement is used to send a value from a method back to its caller.

It also immediately ends the execution of the method.

### Example

```java
public class Main {

    static int add(int a, int b) {
        int sum = a + b;
        return sum;
    }

    public static void main(String[] args) {
        int result = add(10, 20);

        System.out.println("Sum = " + result);
    }
}
```

### Output

```text
Sum = 30
```

### Explanation

1. The `add()` method receives two integer arguments.
2. It calculates their sum.
3. The `return sum;` statement sends the result back.
4. The returned value is stored in `result`.
5. The `main()` method displays the result.

## 4. Different Return Types in Java

A method can return different types of values depending on its purpose.

### A. Integer Return Type

Use `int` when a method needs to return an integer value.

```java
public class Main {

    static int square(int number) {
        return number * number;
    }

    public static void main(String[] args) {
        System.out.println(square(5));
    }
}
```

Output:

```text
25
```

### B. Double Return Type

Use `double` when a method needs to return a decimal value.

```java
public class Main {

    static double calculateAverage(double a, double b) {
        return (a + b) / 2;
    }

    public static void main(String[] args) {
        System.out.println(calculateAverage(10, 20));
    }
}
```

Output:

```text
15.0
```

### C. String Return Type

Use `String` when a method needs to return text.

```java
public class Main {

    static String getMessage() {
        return "Welcome to Java!";
    }

    public static void main(String[] args) {
        String message = getMessage();

        System.out.println(message);
    }
}
```

Output:

```text
Welcome to Java!
```

### D. Boolean Return Type

Use `boolean` when a method needs to return either `true` or `false`.

```java
public class Main {

    static boolean isEven(int number) {
        return number % 2 == 0;
    }

    public static void main(String[] args) {
        System.out.println(isEven(10));
        System.out.println(isEven(7));
    }
}
```

Output:

```text
true
false
```

The method checks whether a number is divisible by 2 without a remainder.

### E. Character Return Type

Use `char` when a method needs to return a single character.

```java
public class Main {

    static char getGrade() {
        return 'A';
    }

    public static void main(String[] args) {
        System.out.println(getGrade());
    }
}
```

Output:

```text
A
```

## 5. What Is the `void` Return Type?

The `void` keyword indicates that a method does not return a value.

A `void` method can perform an operation, such as displaying a message or printing a result, without sending a value back to its caller.

### Example

```java
public class Main {

    static void displayMessage() {
        System.out.println("Learning Java Methods");
    }

    public static void main(String[] args) {
        displayMessage();
    }
}
```

Output:

```text
Learning Java Methods
```

**Important:** A `void` method can use `return;` without a value to end its execution early. However, it cannot return a value.

## 6. Difference Between `void` and Other Return Types

| `void` | Other return types |
|---|---|
| Does not return a value | Returns a value of the declared type |
| Used for operations that do not need to produce a result | Used when the caller needs a result |
| Does not require a return value | Requires a compatible returned value on every possible execution path |
| Example: `static void display()` | Example: `static int add()` |

## 7. Returning a Value and Storing It in a Variable

A returned value can be stored in a variable of a compatible type.

### Example

```java
public class Main {

    static int multiply(int a, int b) {
        return a * b;
    }

    public static void main(String[] args) {
        int result = multiply(6, 7);

        System.out.println("Product = " + result);
    }
}
```

Output:

```text
Product = 42
```

The method calculates the product and returns it. The calling method stores that result in the `result` variable.

## 8. Using a Return Value Directly

A method's returned value does not always need to be stored in a variable. It can also be used directly in an expression or as an argument to another method.

### Example

```java
public class Main {

    static int add(int a, int b) {
        return a + b;
    }

    public static void main(String[] args) {
        System.out.println(add(15, 25));
    }
}
```

Output:

```text
40
```

Here, the returned value from `add()` is passed directly to `System.out.println()`.

## 9. The Return Statement Ends Method Execution

Once a `return` statement executes, the method immediately stops executing.

### Example

```java
public class Main {

    static int getValue() {
        System.out.println("Before return");

        return 10;

        // System.out.println("After return"); 
        // Unreachable statement
    }

    public static void main(String[] args) {
        System.out.println(getValue());
    }
}
```

Output:

```text
Before return
10
```

The statement after `return` is commented out because executable code placed after an unconditional return in the same block is unreachable and causes a compilation error.

## 10. Returning Values Using Conditional Statements

A method can return different values depending on a condition.

### Example

```java
public class Main {

    static String checkNumber(int number) {
        if (number > 0) {
            return "Positive";
        } else if (number < 0) {
            return "Negative";
        } else {
            return "Zero";
        }
    }

    public static void main(String[] args) {
        System.out.println(checkNumber(10));
        System.out.println(checkNumber(-5));
        System.out.println(checkNumber(0));
    }
}
```

Output:

```text
Positive
Negative
Zero
```

Each branch returns a string value. Every possible execution path returns a value, satisfying the method's `String` return type.

## 11. Common Mistakes

### Mistake 1: Returning the Wrong Data Type

Incorrect:

```java
static int getNumber() {
    return "Hello";
}
```

The method declares `int` but attempts to return a `String`.

Correct:

```java
static int getNumber() {
    return 100;
}
```

### Mistake 2: Forgetting the Return Statement

Incorrect:

```java
static int add(int a, int b) {
    int sum = a + b;
}
```

The method declares an `int` return type but does not return a value.

Correct:

```java
static int add(int a, int b) {
    int sum = a + b;
    return sum;
}
```

### Mistake 3: Returning a Value From a `void` Method

Incorrect:

```java
static void display() {
    return 10;
}
```

A `void` method cannot return a value.

Correct:

```java
static void display() {
    System.out.println(10);
}
```

### Mistake 4: Ignoring Possible Execution Paths

Incorrect:

```java
static int check(int number) {
    if (number > 0) {
        return 1;
    }
}
```

The method does not return a value when `number` is zero or negative.

Correct:

```java
static int check(int number) {
    if (number > 0) {
        return 1;
    }

    return 0;
}
```

## 12. Important Points to Remember

- The return type specifies the type of value a method can return.
- The `return` statement sends a value back to the caller.
- A `void` method does not return a value.
- A method with a non-void return type must return a compatible value on every possible execution path.
- A return statement immediately ends the current method execution.
- Returned values can be stored in variables or used directly.
- Methods can return primitive values as well as reference-type values, such as `String` and arrays.

## 13. Best Practices

- Choose a return type that matches the purpose of the method.
- Use meaningful method names.
- Ensure every possible execution path returns a compatible value when required.
- Avoid unnecessary return statements.
- Keep methods focused on a specific task.
- Use `void` when a method performs an action without needing to return a result.

## Next Topic

Continue to [Methods with and Without Parameters](06-Methods-with-and-without-Parameters.md) to understand how methods behave when they receive inputs and when they do not.
