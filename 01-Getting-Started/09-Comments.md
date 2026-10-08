# Comments in Java

Comments are notes written inside source code to explain its purpose, describe important decisions, or provide documentation for other developers.

The Java compiler does not treat ordinary comments as executable statements. Well-written comments improve readability and maintainability without changing the program's intended behavior.

## 1. Why Are Comments Important?

Comments can help developers:

* Explain complex logic.
* Document methods and classes.
* Record important assumptions or design decisions.
* Make unfamiliar code easier to understand.
* Collaborate more effectively on projects.

Consider this example:

```java
public class Calculation {
    public static void main(String[] args) {
        // Calculate the total price of two items
        int firstItem = 100;
        int secondItem = 200;
        int total = firstItem + secondItem;

        System.out.println("Total price: " + total);
    }
}
```

**Output:**

```text
Total price: 300
```

The comment explains the purpose of the calculation. It does not affect the result.

## 2. Single-Line Comments

A single-line comment begins with two forward slashes: `//`.

Everything after `//` on that line is treated as a comment, unless it occurs inside a string or another lexical context where it has a different meaning.

Example:

```java
public class SingleLineComment {
    public static void main(String[] args) {
        // Store the student's age
        int age = 18;

        System.out.println(age); // Print the age
    }
}
```

**Output:**

```text
18
```

Single-line comments are useful for short explanations beside or above a statement.

## 3. Multi-Line Comments

A multi-line comment begins with `/*` and ends with `*/`.

It can span multiple lines, making it useful for longer explanations.

Example:

```java
public class MultiLineComment {
    public static void main(String[] args) {
        /*
         * This program demonstrates
         * a multi-line comment
         * in Java.
         */
        System.out.println("Learning Java");
    }
}
```

**Output:**

```text
Learning Java
```

The entire block between `/*` and `*/` is treated as a comment.

Ordinary block comments cannot be nested reliably. A `/*` inside a block comment does not start a new nested comment.

## 4. Documentation Comments

Documentation comments begin with `/**` and end with `*/`.

They are commonly placed before classes, methods, and other declarations to describe their purpose. The `javadoc` tool can process these comments to generate API documentation.

Example:

```java
/**
 * Provides basic mathematical operations.
 */
public class Calculator {

    /**
     * Returns the sum of two integers.
     *
     * @param a the first integer
     * @param b the second integer
     * @return the sum of a and b
     */
    public static int add(int a, int b) {
        return a + b;
    }
}
```

In this example:

* The first documentation comment describes the class.
* The second describes the `add()` method.
* `@param` documents a parameter.
* `@return` describes the returned value.

Documentation comments are especially useful when building reusable libraries or working on larger projects.

## 5. Comments vs. Code

Consider these two examples.

Without a comment:

```java
int price = 500;
int discount = 50;
int finalPrice = price - discount;
```

With a useful comment:

```java
int price = 500;
int discount = 50;

// Subtract the discount from the original price
int finalPrice = price - discount;
```

Both programs calculate the same result. The second version explains why the subtraction is being performed.

However, comments should add useful information rather than repeat every obvious line.

For example, this comment adds little value:

```java
// Increase count by one
count++;
```

A comment is more helpful when it explains the reason behind a decision or clarifies logic that might otherwise be difficult to understand.

## 6. Can Comments Change Program Output?

No. Ordinary comments do not execute as program instructions.

For example:

```java
public class CommentExample {
    public static void main(String[] args) {
        // System.out.println("This line is commented out");

        System.out.println("This line executes");
    }
}
```

**Output:**

```text
This line executes
```

The first print statement is commented out, so it is not executed.

Comments are useful during development, but they should not replace proper debugging or error handling.

## 7. Common Mistakes

### Forgetting to close a block comment

Incorrect:

```java
/*
This comment never closes properly
System.out.println("Hello");
```

Correct:

```java
/*
This comment is properly closed.
*/
System.out.println("Hello");
```

An unclosed block comment can cause the compiler to treat the remaining source text as part of the comment, potentially leading to compilation errors.

### Using comments to hide broken code permanently

Commenting out code temporarily can be useful during debugging. However, unused or outdated code should generally be removed rather than left commented out indefinitely.

Version control systems such as Git preserve earlier versions of code, so old implementations can be recovered when necessary.

### Writing misleading comments

A comment that no longer matches the code can confuse future readers. Update comments when the related implementation changes.

## 8. Best Practices for Writing Comments

1. Explain why a decision was made when the reason is not obvious.
2. Use meaningful names so that code communicates its purpose.
3. Keep comments concise and accurate.
4. Write documentation comments for public APIs when appropriate.
5. Update or remove outdated comments.
6. Avoid adding comments to every single statement.
7. Prefer clear code over complicated code that requires extensive explanation.

Comments are most effective when they complement readable code rather than compensate for unnecessarily confusing code.

## Conclusion

Java supports three commonly used comment styles: single-line comments, multi-line comments, and documentation comments. Each serves a different purpose, from short explanations to documentation that can be processed by `javadoc`.

Learning to write useful comments is an important step toward producing code that other developers can read, understand, and maintain.

---

*Part of Java Odyssey — Learn. Code. Understand. Repeat.*
