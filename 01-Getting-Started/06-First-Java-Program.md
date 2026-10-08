# Your First Java Program

> Every programmer starts somewhere. This is where your Java coding journey becomes practical.

In this guide, we'll write, compile, and execute our first Java program. We'll also understand what each line means instead of simply memorizing the syntax!

## 1. Writing Your First Program

Create a file named `HelloWorld.java` and write the following code:

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

**Output:**

```text
Hello, World!
```

Let's understand how it works!

## 2. Understanding the Code Line by Line

### `public class HelloWorld`

```java
public class HelloWorld
```

* `public` is an access modifier that allows the class to be accessible from other code, subject to Java's access rules.
* `class` is a keyword used to declare a class.
* `HelloWorld` is the name of the class.

A class is a blueprint that defines the structure and behavior of objects, or can contain members used without creating an object.

**Important:** When a top-level class is declared `public`, its source filename must match the class name. Here, the file is `HelloWorld.java`.

### `public static void main(String[] args)`

```java
public static void main(String[] args)
```

This is the main method declaration used as the standard entry point for a traditional Java application.

Let's break it down:

| Part            | Meaning                                                                          |
| --------------- | -------------------------------------------------------------------------------- |
| `public`        | Makes the method accessible to the Java launcher.                                |
| `static`        | Allows the method to be invoked without first creating an instance of the class. |
| `void`          | Means the method does not return a value.                                        |
| `main`          | The method name recognized as the conventional application entry point.          |
| `String[] args` | An array of strings containing command-line arguments passed to the program.     |

### `System.out.println("Hello, World!");`

```java
System.out.println("Hello, World!");
```

This statement prints text to the standard output, usually your terminal or console.

* `System` is a class provided by Java.
* `out` refers to the standard output stream.
* `println()` prints the supplied value and then ends the current line.
* `"Hello, World!"` is a string literal: the text we want to print.
* `;` marks the end of the statement.

### Curly braces `{ }`

Curly braces mark the beginning and end of a class or method body.

```java
public class HelloWorld {
    public static void main(String[] args) {
        // Statements go here
    }
}
```

The outer pair belongs to the class, while the inner pair belongs to the main method.

## 3. Printing Multiple Lines

You can use `System.out.println()` more than once.

```java
public class Introduction {
    public static void main(String[] args) {
        System.out.println("Welcome to Java.");
        System.out.println("I am learning programming.");
        System.out.println("This is my first program.");
    }
}
```

**Output:**

```text
Welcome to Java.
I am learning programming.
This is my first program.
```

Each `println()` statement prints its content on a separate line.

## 4. Using `print()` Instead of `println()`

Java provides both `print()` and `println()` for displaying output.

```java
public class PrintExample {
    public static void main(String[] args) {
        System.out.print("Hello ");
        System.out.print("Java ");
        System.out.println("Learners");
    }
}
```

**Output:**

```text
Hello Java Learners
```

The difference is:

* `print()` displays content without automatically moving to the next line.
* `println()` displays content and then moves to the next line.

## 5. Using Escape Sequences

Escape sequences let you include special characters in strings.

```java
public class EscapeExample {
    public static void main(String[] args) {
        System.out.println("Name:\tAlex");
        System.out.println("Language:\tJava");
        System.out.println("Hello\nWorld");
        System.out.println("He said, \"Java is interesting.\"");
    }
}
```

**Output:**

```text
Name:   Alex
Language:   Java
Hello
World
He said, "Java is interesting."
```

Common escape sequences include:

| Escape sequence | Meaning               |
| --------------- | --------------------- |
| `\n`            | New line              |
| `\t`            | Horizontal tab        |
| `\"`            | Double quotation mark |
| `\\`            | Backslash             |

The exact spacing produced by a tab can depend on the terminal.

## 6. Compiling and Running the Program

Java source code is saved in a `.java` file. In the traditional compilation workflow, the Java compiler converts it into bytecode stored in a `.class` file.

Suppose your file is named `HelloWorld.java`.

**Step 1: Open a terminal** in the directory containing the file.

**Step 2: Compile the program.**

```bash
javac HelloWorld.java
```

If compilation succeeds, Java creates `HelloWorld.class`.

**Step 3: Run the compiled class.**

```bash
java HelloWorld
```

Expected output:

```text
Hello, World!
```

When launching the class this way, use `HelloWorld`, not `HelloWorld.class`.

## 7. Common Errors and How to Avoid Them

| Error                                      | How to fix it                                                                               |
| ------------------------------------------ | ------------------------------------------------------------------------------------------- |
| Filename and public class name don't match | Use `HelloWorld.java` for `public class HelloWorld`.                                        |
| Missing semicolon                          | Add `;` at the end of statements that require it.                                           |
| Incorrect capitalization                   | Java is case-sensitive: `System` and `system` are different identifiers.                    |
| Missing curly brace                        | Make sure each opening brace has a matching closing brace.                                  |
| Using `java HelloWorld.class`              | Use `java HelloWorld` in the traditional compile-run workflow.                              |
| Running the command in the wrong directory | Open the terminal in the directory containing the source or compiled class, as appropriate. |

## 8. Why Understanding the Code Matters

A Java program is more than a set of lines that produce output. Understanding the class declaration, main method, statements, and syntax helps you read other people's code and debug your own.

As you continue learning, you'll explore variables, data types, operators, input, methods, and object-oriented programming. These concepts will build on the structure introduced here.

**Coming next:** [Java Program Structure](07-Java-Program-Structure.md)

---

*Part of Java Odyssey — Learn. Code. Understand. Repeat.*
