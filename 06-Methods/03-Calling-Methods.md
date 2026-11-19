# Calling Methods in Java

## 1. What Is Method Calling?

**Method calling** is the process of invoking a method so that the statements inside its body can execute.

In Java, defining a method does not automatically execute it. We must call the method to run its code.

For example:

```java
public class Main {

    static void greet() {
        System.out.println("Hello, Java!");
    }

    public static void main(String[] args) {
        greet();
    }
}
```

### Output

```text
Hello, Java!
```

Here, `greet()` is called from the `main()` method, so its body executes.

## 2. Basic Syntax of Calling a Method

The general syntax for calling a method is:

```java
methodName(arguments);
```

Where:

- `methodName` is the name of the method.
- `arguments` are the values passed to the method.
- Parentheses are used even when no arguments are required.
- A semicolon terminates a method call when it is written as a statement.

Example:

```java
displayMessage();
```

This statement calls a method named `displayMessage` that does not accept any arguments.

## 3. Calling a Static Method

A `static` method belongs to the class rather than an individual object.

It can be called directly from another static method in the same class.

### Example

```java
public class Main {

    static void display() {
        System.out.println("Static method executed.");
    }

    public static void main(String[] args) {
        display();
    }
}
```

### Output

```text
Static method executed.
```

A static method can also be called using the class name.

```java
public class Main {

    static void display() {
        System.out.println("Hello from Main!");
    }

    public static void main(String[] args) {
        Main.display();
    }
}
```

### Output

```text
Hello from Main!
```

**Important:** Calling a static method through the class name is generally preferred when accessing it from another class.

## 4. Calling an Instance Method

An instance method belongs to an object of a class.

To call an instance method from a static context, such as `main()`, we generally create an object first.

### Example

```java
public class Main {

    void display() {
        System.out.println("Instance method executed.");
    }

    public static void main(String[] args) {
        Main obj = new Main();

        obj.display();
    }
}
```

### Output

```text
Instance method executed.
```

### Explanation

1. `Main obj = new Main();` creates an object of the `Main` class.
2. `obj` is the reference variable that refers to the object.
3. `obj.display();` calls the instance method using that object.

## 5. Calling a Method With Arguments

Methods can receive values through parameters.

When calling such a method, we provide arguments inside the parentheses.

### Example

```java
public class Main {

    static void greet(String name) {
        System.out.println("Hello, " + name);
    }

    public static void main(String[] args) {
        greet("Ankita");
        greet("Rahul");
    }
}
```

### Output

```text
Hello, Ankita
Hello, Rahul
```

The same method is called twice with different arguments.

The method uses the supplied value each time it executes.

## 6. Calling a Method That Returns a Value

A method can calculate and return a result to the calling code.

The returned value can be stored in a variable or used directly in an expression.

### Example

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

### Output

```text
Sum = 30
```

### Explanation

- `add(10, 20)` calls the `add()` method.
- The values `10` and `20` are passed as arguments.
- The method calculates their sum.
- `return a + b` sends the result back.
- The returned value is stored in `result`.

## 7. Calling One Method From Another Method

A method can call another method to perform a specific task.

This helps divide a program into smaller and reusable parts.

### Example

```java
public class Main {

    static void greet() {
        System.out.println("Welcome to Java!");
    }

    static void startProgram() {
        greet();
        System.out.println("Program started.");
    }

    public static void main(String[] args) {
        startProgram();
    }
}
```

### Output

```text
Welcome to Java!
Program started.
```

### Explanation

1. The `main()` method calls `startProgram()`.
2. The `startProgram()` method calls `greet()`.
3. The `greet()` method displays the welcome message.
4. After `greet()` finishes, execution continues inside `startProgram()`.

This demonstrates how methods can work together to perform a larger task.

## 8. Understanding the Method Call Flow

Consider this program:

```java
public class Main {

    static void first() {
        System.out.println("First method");
    }

    static void second() {
        System.out.println("Second method");
        first();
    }

    public static void main(String[] args) {
        System.out.println("Main method");
        second();
        System.out.println("Program ended");
    }
}
```

### Output

```text
Main method
Second method
First method
Program ended
```

### Execution Flow

1. Program execution begins with `main()`.
2. `main()` prints `Main method`.
3. `main()` calls `second()`.
4. `second()` prints `Second method`.
5. `second()` calls `first()`.
6. `first()` prints `First method` and finishes.
7. Execution returns to `second()`, which finishes.
8. Execution returns to `main()`.
9. `main()` prints `Program ended`.

When a method finishes, execution returns to the point immediately after the method call.

## 9. Calling Methods Multiple Times

A method can be called any number of times, provided the program's execution reaches those calls.

### Example

```java
public class Main {

    static void printMessage() {
        System.out.println("Learning Java step by step.");
    }

    public static void main(String[] args) {
        printMessage();
        printMessage();
        printMessage();
    }
}
```

### Output

```text
Learning Java step by step.
Learning Java step by step.
Learning Java step by step.
```

The method definition is written once, but its code executes three times.

## 10. Common Mistakes While Calling Methods

### Mistake 1: Forgetting Parentheses

Incorrect:

```java
display;
```

Correct:

```java
display();
```

### Mistake 2: Calling an Instance Method Directly From a Static Context

Incorrect:

```java
public class Main {

    void display() {
        System.out.println("Hello");
    }

    public static void main(String[] args) {
        display();
    }
}
```

Correct:

```java
public class Main {

    void display() {
        System.out.println("Hello");
    }

    public static void main(String[] args) {
        Main obj = new Main();
        obj.display();
    }
}
```

### Mistake 3: Passing the Wrong Number of Arguments

If a method requires two arguments, calling it with only one argument causes a compilation error.

```java
static void add(int a, int b) {
    System.out.println(a + b);
}

// Incorrect call
add(10);
```

Correct call:

```java
add(10, 20);
```

### Mistake 4: Using an Incompatible Argument Type

A method expecting an `int` argument cannot directly accept a `String` argument.

```java
static void display(int number) {
    System.out.println(number);
}

// Incorrect call
display("Hello");
```

## 11. Important Points to Remember

- A method executes when it is called.
- A method call uses the method name followed by parentheses.
- Arguments are supplied when calling methods that require parameters.
- Static methods can be called using the class name.
- Instance methods are called using an object reference.
- A method can call another method.
- After a method finishes, execution returns to its caller.
- A method can be called multiple times.

## Next Topic

Continue to [Parameters and Arguments](04-Parameters-and-Arguments.md) to understand how methods receive input values and how parameters differ from arguments.
