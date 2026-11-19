# Methods With and Without Parameters in Java

## 1. Introduction

In Java, methods can be classified according to whether they accept input values.

A method may:

- Accept no parameters.
- Accept one parameter.
- Accept multiple parameters.

Parameters allow methods to work with different input values, making them more flexible and reusable.

Understanding methods with and without parameters is important for writing organized Java programs.

## 2. What Is a Method Without Parameters?

A **method without parameters** is a method that does not accept any input values from the calling code.

Empty parentheses are used in its method definition.

### Syntax

```java
returnType methodName() {
    // Method body
}
```

### Example

```java
public class Main {

    static void greet() {
        System.out.println("Welcome to Java!");
    }

    public static void main(String[] args) {
        greet();
    }
}
```

### Output

```text
Welcome to Java!
```

### Explanation

- `greet()` is the method name.
- The empty parentheses indicate that the method does not accept parameters.
- `void` indicates that the method does not return a value.
- The method displays a message when called.

## 3. What Is a Method With Parameters?

A **method with parameters** accepts one or more input values through variables declared in its method definition.

These values can be used inside the method to perform different operations.

### Syntax

```java
returnType methodName(dataType parameter1, dataType parameter2) {
    // Method body
}
```

### Example

```java
public class Main {

    static void greet(String name) {
        System.out.println("Hello, " + name);
    }

    public static void main(String[] args) {
        greet("Ankita");
    }
}
```

### Output

```text
Hello, Ankita
```

### Explanation

- `String name` is the parameter.
- `"Ankita"` is the argument.
- The method receives the argument and uses it to display the message.

## 4. Method Without Parameters

A method without parameters performs its task without receiving input through its method call.

### Example: Displaying a Message

```java
public class Main {

    static void displayMessage() {
        System.out.println("Learning Java step by step.");
    }

    public static void main(String[] args) {
        displayMessage();
        displayMessage();
    }
}
```

### Output

```text
Learning Java step by step.
Learning Java step by step.
```

The method can be called multiple times without passing any arguments.

## 5. Method With One Parameter

A method can accept a single parameter to work with a supplied value.

### Example: Checking an Even Number

```java
public class Main {

    static void checkEven(int number) {
        if (number % 2 == 0) {
            System.out.println(number + " is even.");
        } else {
            System.out.println(number + " is odd.");
        }
    }

    public static void main(String[] args) {
        checkEven(10);
        checkEven(7);
    }
}
```

### Output

```text
10 is even.
7 is odd.
```

The same method checks different numbers by accepting different arguments.

## 6. Method With Multiple Parameters

A method can accept two or more parameters to perform operations using multiple input values.

### Example: Adding Two Numbers

```java
public class Main {

    static void add(int a, int b) {
        int sum = a + b;
        System.out.println("Sum = " + sum);
    }

    public static void main(String[] args) {
        add(10, 20);
        add(15, 25);
    }
}
```

### Output

```text
Sum = 30
Sum = 40
```

### Explanation

- `int a` and `int b` are parameters.
- `10, 20` and `15, 25` are arguments supplied during the method calls.
- The method calculates and displays the sum for each pair.

## 7. Methods With Different Data Types of Parameters

A method can accept parameters of different data types.

### Example

```java
public class Main {

    static void displayDetails(String name, int age, double marks) {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Marks: " + marks);
    }

    public static void main(String[] args) {
        displayDetails("Ankita", 19, 92.5);
    }
}
```

### Output

```text
Name: Ankita
Age: 19
Marks: 92.5
```

The method accepts:

- A `String` parameter for the name.
- An `int` parameter for the age.
- A `double` parameter for the marks.

Each argument must be compatible with its corresponding parameter.

## 8. Difference Between Methods With and Without Parameters

| Without Parameters | With Parameters |
|---|---|
| Does not accept input through its method call | Accepts input through its method call |
| Uses empty parentheses | Contains parameter declarations inside parentheses |
| Performs tasks without receiving method-call arguments | Uses received values to perform tasks |
| Example: `display()` | Example: `display(int number)` |

## 9. Practical Example: Calculating the Area of a Rectangle

Let's compare both types of methods using a practical example.

### A. Without Parameters

```java
public class Main {

    static void calculateArea() {
        int length = 10;
        int breadth = 5;

        int area = length * breadth;

        System.out.println("Area = " + area);
    }

    public static void main(String[] args) {
        calculateArea();
    }
}
```

### Output

```text
Area = 50
```

Here, the values of `length` and `breadth` are defined inside the method.

### B. With Parameters

```java
public class Main {

    static void calculateArea(int length, int breadth) {
        int area = length * breadth;

        System.out.println("Area = " + area);
    }

    public static void main(String[] args) {
        calculateArea(10, 5);
        calculateArea(8, 4);
    }
}
```

### Output

```text
Area = 50
Area = 32
```

Here, the method accepts different values through parameters, so it can calculate the area of different rectangles without changing its definition.

## 10. Important Points to Remember

- Parameters are declared inside the method definition.
- Arguments are supplied when the method is called.
- A method without parameters uses empty parentheses.
- A method can accept one or multiple parameters.
- Parameters can have different data types.
- The number and types of arguments must be compatible with the method's parameters.
- Methods with parameters are useful when the same operation needs to work with different inputs.
- Methods without parameters are useful when a task does not require input through the method call.

## 11. Best Practices

- Use meaningful parameter names.
- Choose appropriate data types for parameters.
- Avoid unnecessary parameters.
- Use methods with parameters when the operation needs different inputs.
- Use methods without parameters when the method does not need input from its caller.
- Keep methods focused on a specific task.

## Next Topic

Continue to [Methods with and Without Return Values](07-Methods-with-and-without-Return-Values.md) to understand how methods can perform operations with or without returning results.
