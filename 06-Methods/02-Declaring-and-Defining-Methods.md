# Declaring and Defining Methods in Java

## 1. Introduction

In Java, methods are used to organize code into reusable blocks that perform specific tasks.

Before using a method, we generally need to declare and define it inside a class.

A method declaration specifies important information about the method, such as its name, return type, and parameters. The method definition provides the actual implementation through its body.

Understanding these concepts is essential for writing structured Java programs.

## 2. What Is Method Declaration?

A **method declaration** specifies the method's signature and other relevant information.

The method signature consists of:

- Method name
- Parameter types and their order

In Java, the return type and access modifier are part of the method declaration, but they are not part of the method signature.

### Example

```java
public static int calculateSum(int a, int b);
```

This is an illustrative method declaration. Java does not allow a standalone method declaration ending with a semicolon inside an ordinary class. An abstract method or an interface method can have a declaration without a method body.

## 3. What Is Method Definition?

A **method definition** provides the complete implementation of a method, including its method header and body.

The method body contains the statements that execute when the method is called.

### Example

```java
public class Main {

    public static int calculateSum(int a, int b) {
        return a + b;
    }

    public static void main(String[] args) {
        int result = calculateSum(10, 20);
        System.out.println("Sum = " + result);
    }
}
```

### Output

```text
Sum = 30
```

### Explanation

- `public` is the access modifier.
- `static` allows the method to be called through the class without creating an object.
- `int` is the return type.
- `calculateSum` is the method name.
- `int a` and `int b` are parameters.
- `return a + b` returns the calculated result.

## 4. General Syntax of a Method

```java
accessModifier static returnType methodName(parameterList) {
    // Method body
    // Statements

    return value;
}
```

### Components Explained

| Component | Description |
|---|---|
| Access modifier | Controls the accessibility of the method |
| `static` | Makes the method belong to the class |
| Return type | Specifies the type of value returned |
| Method name | Identifies the method |
| Parameter list | Defines the inputs accepted by the method |
| Method body | Contains the executable statements |
| Return statement | Sends a value back to the caller when required |

**Note:** The `static` keyword is optional. The `return` statement is required when a method must return a value, but a `void` method does not need to return one.

## 5. Declaring and Defining a Method Without Parameters

A method does not always need input values.

### Example

```java
public class Main {

    static void displayMessage() {
        System.out.println("Welcome to Java Programming!");
    }

    public static void main(String[] args) {
        displayMessage();
    }
}
```

### Output

```text
Welcome to Java Programming!
```

### Explanation

- `displayMessage()` is the method name.
- `void` indicates that the method does not return a value.
- The empty parentheses indicate that it does not accept parameters.
- The method displays a message when called.

## 6. Declaring and Defining a Method With Parameters

A method can accept information through parameters.

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
- `"Ankita"` is the argument passed during the method call.
- The method uses the received value to display a personalized message.

## 7. Method Declaration vs Method Definition

| Method Declaration | Method Definition |
|---|---|
| Specifies method information | Provides the implementation |
| Does not necessarily contain a body | Contains a method body |
| Can be used for abstract methods and interface declarations | Used when implementing the method |
| An ordinary class cannot contain a standalone body-less method declaration | A concrete method in a class has a body |

**Important:** In everyday Java programming, people often use the term *method declaration* to refer to the complete method header, even when discussing a method with a body. The exact meaning depends on the context.

## 8. Important Rules for Defining Methods

1. A method must be defined inside a class, interface, or enum as permitted by Java.
2. Every method must have a valid name and return type.
3. A method that returns a value must return a compatible value on every possible execution path.
4. A `void` method does not return a value.
5. A method can have zero, one, or multiple parameters.
6. Java does not allow two methods in the same class with identical method signatures.
7. Methods cannot be defined inside other methods.

## 9. Example: A Method Performing a Calculation

```java
public class Main {

    static int multiply(int a, int b) {
        int product = a * b;
        return product;
    }

    public static void main(String[] args) {
        int answer = multiply(5, 4);

        System.out.println("Product = " + answer);
    }
}
```

### Output

```text
Product = 20
```

The `multiply()` method accepts two integer parameters, calculates their product, and returns the result to the calling method.

## 10. Best Practices

- Choose meaningful method names that describe their purpose.
- Keep each method focused on a specific task.
- Use appropriate return types.
- Avoid unnecessarily long methods.
- Use parameters to make methods reusable with different inputs.
- Follow Java naming conventions by using lower camel case for method names, such as `calculateTotal()`.

## Next Topic

Continue to [Calling Methods](03-Calling-Methods.md) to understand how to invoke methods and execute their code in Java.
