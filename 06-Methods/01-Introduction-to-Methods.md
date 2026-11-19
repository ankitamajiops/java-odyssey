# Introduction to Methods in Java

## 1. What Is a Method in Java?

A **method** in Java is a block of code designed to perform a specific task. It executes when it is called or invoked.

Methods help divide a large program into smaller, manageable parts. Instead of writing the same code repeatedly, we can define a method once and call it whenever required.

For example, a program that calculates the sum of two numbers can use a separate method to perform the addition.

## 2. Why Are Methods Used?

Methods are used to organize program logic and make code easier to understand and maintain.

Consider a program that needs to calculate the sum of two numbers at multiple places. Without methods, we might write the same addition statements repeatedly.

By creating a method for addition, we can reuse the same logic whenever needed.

### Main Advantages of Methods

1. **Code Reusability:** Write a block of code once and use it multiple times.
2. **Code Organization:** Divide a large program into smaller logical sections.
3. **Readability:** Make programs easier to understand.
4. **Easy Maintenance:** Modify a method in one place instead of changing repeated code.
5. **Reduced Code Duplication:** Avoid writing the same statements repeatedly.
6. **Modularity:** Develop and test individual parts of a program separately.

## 3. Basic Structure of a Method

A Java method generally follows this structure:

```java
accessModifier static returnType methodName(parameters) {
    // Method body
    // Statements to execute

    return value;
}
```

### Explanation of Each Part

| Component | Meaning |
|---|---|
| Access modifier | Determines where the method can be accessed, such as `public` or `private` |
| `static` | Indicates that the method belongs to the class rather than an individual object |
| Return type | Specifies the type of value returned by the method |
| Method name | The name used to identify and call the method |
| Parameters | Inputs received by the method |
| Method body | Contains the statements executed when the method is called |
| `return` | Sends a value back to the calling code when required |

**Note:** Not every method needs to be `static`, and a method with return type `void` does not return a value.

## 4. A Simple Example of a Method

Let's create a Java program with a method that displays a message.

### Program

```java
public class Main {

    static void greet() {
        System.out.println("Welcome to Java Methods!");
    }

    public static void main(String[] args) {
        greet();
    }
}
```

### Output

```text
Welcome to Java Methods!
```

### Explanation

1. `public class Main` declares the class.
2. `static void greet()` defines a method named `greet`.
3. `System.out.println()` displays the message.
4. `main()` is the entry point of the program.
5. `greet()` calls the method from inside `main()`.
6. When the method is called, its body executes.

The method is defined separately and called whenever its functionality is needed.

## 5. Understanding Method Definition and Method Calling

There are two important concepts when working with methods.

### Method Definition

A method definition contains the method's name, return type, parameters, and body.

Example:

```java
static void display() {
    System.out.println("Hello Java");
}
```

### Method Calling

A method call executes the statements inside the defined method.

Example:

```java
display();
```

A method can be called multiple times.

```java
public class Main {

    static void display() {
        System.out.println("Hello Java");
    }

    public static void main(String[] args) {
        display();
        display();
        display();
    }
}
```

### Output

```text
Hello Java
Hello Java
Hello Java
```

The same method executes three times without requiring its code to be written repeatedly.

## 6. A Program Using Multiple Methods

A Java class can contain multiple methods, each responsible for a different task.

### Program

```java
public class Main {

    static void greet() {
        System.out.println("Welcome!");
    }

    static void displayCourse() {
        System.out.println("Learning Java Programming");
    }

    static void displayMessage() {
        System.out.println("Keep Practicing!");
    }

    public static void main(String[] args) {
        greet();
        displayCourse();
        displayMessage();
    }
}
```

### Output

```text
Welcome!
Learning Java Programming
Keep Practicing!
```

### Explanation

- `greet()` displays a welcome message.
- `displayCourse()` displays the course name.
- `displayMessage()` displays an encouraging message.
- The `main()` method calls all three methods in sequence.

Each method performs one specific task, making the program easier to organize.

## 7. Methods and Code Reusability

One of the most important advantages of methods is code reusability.

Consider the following example:

```java
public class Main {

    static void calculateSum() {
        int a = 10;
        int b = 20;

        System.out.println("Sum = " + (a + b));
    }

    public static void main(String[] args) {
        calculateSum();
        calculateSum();
        calculateSum();
    }
}
```

### Output

```text
Sum = 30
Sum = 30
Sum = 30
```

The addition logic is written only once but executed three times.

This reduces duplication and makes the program easier to maintain.

## 8. Important Points to Remember

- A method is a reusable block of code that performs a specific task.
- A method executes when it is called.
- A Java class can contain multiple methods.
- Methods help improve readability, modularity, and maintainability.
- Methods can accept inputs through parameters.
- Methods can return values to the calling code.
- The `main()` method is the entry point of a standard Java application.
- A method can be called multiple times.

## Next Topic

Continue to [Declaring and Defining Methods](02-Declaring-and-Defining-Methods.md) to understand how to create methods in Java and write their definitions correctly.
