# Methods with and Without Return Values in Java

## 1. Introduction

In Java, methods can be classified based on whether they return a value after performing a task.

A method may:

- Perform an operation and return a result.
- Perform an operation without returning any value.

The return type of a method determines what kind of value it can send back to the calling method.

There are two common categories:

1. Methods with return values.
2. Methods without return values (`void` methods).

## 2. Methods with Return Values

A method with a return value sends a result back to the place where it was called.

The return type specifies the type of value the method must return.

### Syntax

```java
returnType methodName(parameters) {
    // Statements
    return value;
}
```

Here:
- `returnType` specifies the data type of the returned value.
- `methodName` is the name of the method.
- `parameters` are optional inputs.
- `return` sends a value back to the caller.

### Example: Method Returning an Integer

```java
public class Main {

    static int add(int a, int b) {
        return a + b;
    }

    public static void main(String[] args) {
        int result = add(10, 20);

        System.out.println("Sum = " + result);
    }
}
```

**Output:**

```text
Sum = 30
```

**Explanation:**

1. The `add()` method accepts two integer parameters.
2. It calculates their sum.
3. The `return` statement sends the result back.
4. The returned value is stored in the `result` variable.
5. The result is printed.

### Using a Returned Value Directly

A returned value can also be used directly in an expression.

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

**Output:**

```text
25
```

The method calculates the square and returns it directly to `println()`.

## 3. Methods Without Return Values

A method that performs a task but does not send any value back uses the `void` return type.

Such methods are commonly used for displaying messages, printing results, or performing actions.

### Syntax

```java
void methodName(parameters) {
    // Statements
}
```

### Example: Void Method

```java
public class Main {

    static void displayMessage() {
        System.out.println("Welcome to Java!");
    }

    public static void main(String[] args) {
        displayMessage();
    }
}
```

**Output:**

```text
Welcome to Java!
```

**Explanation:**

1. `displayMessage()` is declared with the `void` return type.
2. It prints a message.
3. It does not return any value.
4. The `main()` method calls it to execute the task.

## 4. Difference Between Return and Void Methods

| Feature | Method with Return Value | Void Method |
|---|---|---|
| Return type | `int`, `double`, `String`, etc. | `void` |
| Returns a value | Yes | No |
| Uses `return` | Returns a compatible value | May use `return;` to exit early |
| Result can be stored | Yes | No returned result to store |
| Common purpose | Calculations and obtaining results | Performing actions |

## 5. A Method Can Return Different Values

A method can use conditional statements to decide which value to return.

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
        System.out.println(checkNumber(15));
        System.out.println(checkNumber(-8));
        System.out.println(checkNumber(0));
    }
}
```

**Output:**

```text
Positive
Negative
Zero
```

Each possible path returns a `String` value.

## 6. Using return in a Void Method

A `void` method can use `return;` without a value to end its execution early.

```java
public class Main {

    static void checkAge(int age) {
        if (age < 0) {
            System.out.println("Invalid age");
            return;
        }

        System.out.println("Age = " + age);
    }

    public static void main(String[] args) {
        checkAge(-5);
        checkAge(20);
    }
}
```

**Output:**

```text
Invalid age
Age = 20
```

When the age is negative, `return;` exits the method immediately. Otherwise, execution continues to the next statement.

## 7. Important Rules

1. A non-void method must return a value compatible with its declared return type.
2. Every possible execution path in a non-void method must return an appropriate value.
3. A `void` method cannot return a value.
4. A `void` method may use `return;` to exit early.
5. A returned value can be stored in a variable, passed to another method, or used in an expression.
6. The return type and the presence of parameters are independent. A method can have parameters and still be `void`, or have no parameters and still return a value.

## 8. Common Mistakes

### Mistake 1: Forgetting the return statement

Incorrect:

```java
static int getNumber() {
    int number = 10;
}
```

Correct:

```java
static int getNumber() {
    int number = 10;
    return number;
}
```

### Mistake 2: Returning a value from a void method

Incorrect:

```java
static void display() {
    return 10;
}
```

Correct:

```java
static void display() {
    System.out.println(10);
}
```

### Mistake 3: Using an incompatible return type

Incorrect:

```java
static int getName() {
    return "Ankita";
}
```

Correct:

```java
static String getName() {
    return "Ankita";
}
```

## 9. Best Practices

- Choose a return type that accurately represents the result.
- Use `void` when the method only needs to perform an action.
- Give methods meaningful names that describe their purpose.
- Make sure every possible path in a non-void method returns a value.
- Avoid unnecessary printing inside methods that should calculate and return results.

## 10. Summary

Methods with return values send results back to the caller, while `void` methods perform tasks without returning a value.

The `return` statement is used to send a value from a non-void method or to exit a method early. Understanding this distinction helps in writing reusable, organized, and readable Java programs.

---

**Next Topic:** [Static Methods](08-Static-Methods.md)
