# Understanding the `main()` Method in Java

The `main()` method is the conventional entry point of a standard Java application. It provides the starting point from which the Java launcher begins executing the program.

Understanding its declaration is essential because nearly every beginner Java program uses it!

## 1. Basic Syntax

```java
public class MainExample {
    public static void main(String[] args) {
        System.out.println("Program started");
    }
}
```

**Output:**

```text
Program started
```

The method declaration is:

```java
public static void main(String[] args)
```

Let's understand each component!

## 2. Understanding Each Keyword

### `public`

`public` is an access modifier. It allows the Java launcher to access the method when starting a traditional Java application.

```java
public static void main(String[] args)
```

For the standard entry-point form taught to beginners, keep `main()` public.

### `static`

`static` means the method belongs to the class rather than to a particular object.

The Java launcher can invoke the conventional main method without first creating an instance of the class.

Compare this with an instance method:

```java
public class Example {
    void display() {
        System.out.println("Instance method");
    }

    public static void main(String[] args) {
        Example obj = new Example();
        obj.display();
    }
}
```

**Output:**

```text
Instance method
```

Here, `display()` is an instance method, so the program creates an `Example` object before calling it.

### `void`

`void` indicates that the method does not return a value to its caller.

```java
public static void main(String[] args)
```

For example, this method prints a message but does not return a result:

```java
static void greet() {
    System.out.println("Hello!");
}
```

By contrast, a method declared with `int` as its return type must return an integer value along every normally completing path.

### `main`

`main` is the method name recognized by the Java launcher as the conventional application entry point.

Java is case-sensitive, so `main` and `Main` are different identifiers.

Use lowercase `main` in the standard declaration.

### `String[] args`

This parameter receives command-line arguments supplied when the application is launched.

* `String` is the Java class used to represent text.
* `[]` indicates an array.
* `args` is the parameter name; you may choose another valid name, but `args` is conventional.

For example:

```java
public class ArgumentsExample {
    public static void main(String[] args) {
        System.out.println(args.length);
    }
}
```

If you launch the program with three arguments:

```bash
java ArgumentsExample red blue green
```

**Output:**

```text
3
```

The array contains three strings: `"red"`, `"blue"`, and `"green"`.

If no command-line arguments are supplied, the array is empty.

## 3. Why Is `main()` Important?

A Java source file can contain many classes and methods. For a traditional application, the Java launcher needs a recognized entry point to know where to begin.

Consider this program:

```java
public class Start {
    static void first() {
        System.out.println("First method");
    }

    public static void main(String[] args) {
        System.out.println("Starting program");
        first();
    }
}
```

**Output:**

```text
Starting program
First method
```

Execution begins with `main()`. The call to `first()` then runs that method.

Defining another method does not automatically make it the starting point of the application.

## 4. Can We Write `main()` Differently?

Java supports method overloading, so a class can contain other methods named `main` with different parameter lists.

```java
public class MainOverload {
    public static void main(String[] args) {
        System.out.println("Standard entry point");
        main(10);
    }

    static void main(int number) {
        System.out.println(number);
    }
}
```

**Output:**

```text
Standard entry point
10
```

The Java launcher selects the recognized application entry point; the overloaded `main(int number)` method is called explicitly by the program.

For beginner programs, use the standard declaration:

```java
public static void main(String[] args)
```

Newer Java releases have introduced additional flexible options for application entry points, but the traditional declaration remains important for learning and compatibility.

## 5. What Happens If We Remove a Keyword?

For the standard beginner entry point:

| Change                  | Explanation                                                                           |
| ----------------------- | ------------------------------------------------------------------------------------- |
| Remove `public`         | The method no longer matches the traditional public entry-point form.                 |
| Remove `static`         | The method becomes an instance method rather than the traditional static entry point. |
| Change `void` to `int`  | It no longer matches the conventional entry-point signature.                          |
| Change `main` to `Main` | It becomes a different method name.                                                   |
| Remove `String[] args`  | It no longer matches the traditional parameter form.                                  |

These changes may prevent the Java launcher from recognizing the method as the expected entry point, depending on the Java version and launch mode.

## 6. Common Beginner Mistakes

### Mistake 1: Incorrect capitalization

```java
public static void Main(String[] args)
```

`Main` is not the same as `main`.

### Mistake 2: Incorrect parameter type

```java
public static void main(int[] args)
```

The traditional entry point uses a string array, not an integer array.

### Mistake 3: Forgetting the class braces

```java
public class Example {
    public static void main(String[] args) {
        System.out.println("Hello");
    }
}
```

Make sure the class and method bodies have matching opening and closing braces.

### Mistake 4: Assuming every method must be static

Only the conventional entry-point method needs to follow the relevant launcher requirements. Other methods can be instance methods or static methods, depending on their purpose.

## 7. A Complete Example

```java
public class StudentProfile {
    static void showMessage() {
        System.out.println("Welcome to Java");
    }

    public static void main(String[] args) {
        String name = "Alex";
        int year = 1;

        showMessage();

        System.out.println("Name: " + name);
        System.out.println("Year: " + year);
    }
}
```

**Output:**

```text
Welcome to Java
Name: Alex
Year: 1
```

This example demonstrates how the `main()` method coordinates program execution by calling another method and printing stored values.

## Conclusion

The `main()` method is the conventional starting point for a traditional Java application. Its standard declaration uses `public`, `static`, `void`, the name `main`, and a `String[]` parameter.

Understanding these components will help you recognize Java program entry points and read beginner programs with confidence.

**Coming next:** [Comments in Java](09-Comments.md)

---

*Part of Java Odyssey — Learn. Code. Understand. Repeat.*
