# Java Program Structure

A Java program follows a structure that helps the compiler understand the code and helps developers organize its components.

Understanding this structure is essential before moving on to variables, methods, classes, and object-oriented programming!

## 1. A Basic Java Program

Consider the following example:

```java
public class Student {
    public static void main(String[] args) {
        String name = "Alex";
        int age = 18;

        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
    }
}
```

**Output:**

```text
Name: Alex
Age: 18
```

Let's examine the different parts of this program!

## 2. Package Declaration

A package groups related Java classes and interfaces into a namespace.

Example:

```java
package com.example.student;
```

A package declaration, when present, normally appears at the beginning of the source file, before import declarations and type declarations.

Packages help organize larger projects and avoid naming conflicts.

For example, two different packages can contain classes with the same simple name.

A package declaration is optional. Our basic `Student` example does not require one.

## 3. Import Statements

Import statements allow you to refer to accessible types or static members using shorter names instead of their fully qualified names.

Example:

```java
import java.util.Scanner;
```

Now you can refer to `Scanner` directly rather than writing `java.util.Scanner` every time.

Consider this example:

```java
import java.util.Scanner;

public class UserInput {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.print("Enter your name: ");
        String name = input.nextLine();

        System.out.println("Hello, " + name);

        input.close();
    }
}
```

If the user enters `Alex`, the output is:

```text
Enter your name: Alex
Hello, Alex
```

The `Scanner` class is commonly used to read input. We will study input handling in a separate topic.

Not every Java program needs an import statement.

## 4. Class Declaration

A class defines a type that can contain fields, constructors, methods, and other members.

Example:

```java
public class Student {
    // Fields and methods belong here
}
```

Here:

* `public` is an access modifier.
* `class` is a Java keyword.
* `Student` is the class name.
* The curly braces enclose the class body.

If a top-level class is declared `public`, its source file must have the same name as the class, followed by `.java`.

For example:

```text
Student.java
```

contains:

```java
public class Student {
}
```

Java is case-sensitive, so `Student` and `student` are different names.

## 5. The Main Method

For a traditional Java application, execution normally begins at the main method recognized by the Java launcher.

```java
public static void main(String[] args) {
    System.out.println("Program started");
}
```

The method declaration contains several components:

| Component       | Purpose                                                     |
| --------------- | ----------------------------------------------------------- |
| `public`        | Allows the launcher to access the method                    |
| `static`        | Allows invocation without creating an instance of the class |
| `void`          | Indicates that the method returns no value                  |
| `main`          | The conventional entry-point method name                    |
| `String[] args` | Receives command-line arguments                             |

Java supports other application launch arrangements and newer source-file launching features, but this is the standard entry-point form beginners should recognize.

## 6. Statements and Expressions

A statement is an instruction that performs an action. An expression is a construct that produces a value.

Example:

```java
int total = 10 + 20;
System.out.println(total);
```

In this example:

* `10 + 20` is an expression that evaluates to `30`.
* `int total = 10 + 20;` is a variable declaration and initialization statement.
* `System.out.println(total);` is a method invocation statement.

Many Java statements end with a semicolon.

## 7. Variables and Data Types

Variables store values that a program can use.

Example:

```java
int age = 18;
double percentage = 92.5;
char grade = 'A';
boolean passed = true;
String name = "Alex";
```

Here:

* `int` stores an integer value.
* `double` stores a floating-point number.
* `char` stores a single UTF-16 code unit.
* `boolean` stores `true` or `false`.
* `String` represents text.

The first four are primitive types. `String` is a reference type.

Variables make programs flexible because values can be stored, updated, and used in calculations.

## 8. Methods

Methods group statements into reusable units of code.

Example:

```java
public class Calculator {
    static int add(int a, int b) {
        return a + b;
    }

    public static void main(String[] args) {
        int result = add(10, 20);
        System.out.println(result);
    }
}
```

**Output:**

```text
30
```

In this example, `add()` receives two integers and returns their sum. The main method calls it and prints the result.

Methods can accept parameters, return values, and help divide a program into manageable parts.

## 9. Comments

Comments explain code to human readers and are ignored as executable instructions.

### Single-line comment

```java
// This is a single-line comment
int age = 18;
```

### Multi-line comment

```java
/*
 This is a multi-line comment.
 It can span several lines.
*/
```

### Documentation comment

```java
/**
 * Returns the sum of two integers.
 */
static int add(int a, int b) {
    return a + b;
}
```

Documentation comments can be processed by the `javadoc` tool to generate API documentation.

Comments should explain purpose or reasoning rather than repeat what the code already makes obvious.

## 10. A Typical Java Source File

A source file may contain the following components:

```text
Optional package declaration
Optional import declarations
Class or interface declarations
    Fields
    Constructors
    Methods
```

This is a conceptual outline, not a requirement that every file contain all these elements.

For example, a very small Java program may contain only one class with a main method.

## 11. Important Syntax Rules

* Java is case-sensitive.
* A public top-level class must match its source filename.
* Curly braces define class, method, and control-flow blocks.
* Most statements end with a semicolon.
* Strings use double quotation marks, such as `"Hello"`.
* Character literals use single quotation marks, such as `'A'`.
* Whitespace and indentation help readability, even when they do not affect program meaning.

## Conclusion

Understanding Java program structure makes it easier to read, write, and debug code. The class declaration defines the main organizational unit, the main method provides the conventional entry point, and statements inside methods describe the actions the program performs.

As you progress, you will learn how variables, operators, conditions, loops, and methods work together within this structure.

**Coming next:** [Understanding the main Method](08-main-Method.md)

---

*Part of Java Odyssey — Learn. Code. Understand. Repeat.*
