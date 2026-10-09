# The `var` Keyword in Java

The `var` keyword was introduced in **Java 10** to allow local variable type inference. It enables Java to determine a variable's type from the value assigned to it, reducing unnecessary repetition in code.

Although `var` makes variable declarations shorter, Java remains a statically typed language. The variable's type is determined at compile time and cannot change afterward.

## 1. Declaring Variables Using `var`

When you declare a local variable using `var`, the compiler infers its type from the initializer.

Example:

```java
public class Main {
    public static void main(String[] args) {
        var age = 18;
        var name = "Ananya";
        var price = 99.50;
        var isStudent = true;

        System.out.println(age);
        System.out.println(name);
        System.out.println(price);
        System.out.println(isStudent);
    }
}
```

Output:

```text
18
Ananya
99.5
true
```

The compiler infers the following types:

- `age` is an `int`.
- `name` is a `String`.
- `price` is a `double`.
- `isStudent` is a `boolean`.

You do not need to write these types explicitly because the compiler determines them from the initializer.

## 2. How Type Inference Works

Type inference means the compiler determines the variable's type from the expression used to initialize it.

Consider the following example:

```java
var number = 10;
number = 25;
```

This is valid because `number` is inferred to be an `int`, and `25` is also an `int`.

However, the following code is invalid:

```java
var number = 10;
number = "Hello";
```

This causes a compilation error because `number` has already been inferred as an `int`. Assigning a `String` to it is not allowed.

Therefore, `var` does not make Java dynamically typed.

## 3. Rules for Using `var`

### Rule 1: An Initializer Is Required

A `var` variable must be initialized when it is declared because the compiler needs a value or expression to infer its type.

Invalid:

```java
var age;
```

Valid:

```java
var age = 18;
```

### Rule 2: `var` Is Only for Local Variables

The `var` keyword can be used for local variables declared inside methods, constructors, and initializer blocks. It cannot be used to declare instance variables or static fields.

Invalid:

```java
class Student {
    var age = 18;
}
```

Valid:

```java
class Student {
    int age = 18;

    void display() {
        var marks = 85;
        System.out.println(marks);
    }
}
```

### Rule 3: A `var` Variable Cannot Be Initialized With Only `null`

The compiler cannot infer a specific type from `null` alone.

Invalid:

```java
var name = null;
```

Valid:

```java
String name = null;
```

### Rule 4: Multiple Variables Cannot Be Declared Together Using `var`

Invalid:

```java
var a = 10, b = 20;
```

Valid:

```java
var a = 10;
var b = 20;
```

### Rule 5: `var` Cannot Be Used for Method Parameters or Return Types

Method parameters and return types must have explicitly declared types.

Invalid:

```java
var calculate(int a, int b) {
    return a + b;
}
```

Valid:

```java
int calculate(int a, int b) {
    return a + b;
}
```

### Rule 6: The Inferred Type Is Fixed

Once the compiler infers a variable's type, that type does not change.

```java
var score = 95;
score = 100;       // Valid
// score = "A";    // Compilation error
```

Here, `score` remains an `int`.

## 4. Using `var` With Collections and Objects

The `var` keyword can also be used with objects and collection types when the initializer provides enough information for the compiler to infer the type.

Example:

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        var message = new String("Hello Java");
        var numbers = new ArrayList<Integer>();

        numbers.add(10);
        numbers.add(20);

        System.out.println(message);
        System.out.println(numbers);
    }
}
```

Output:

```text
Hello Java
[10, 20]
```

In this example:

- `message` is inferred to have the type `String`.
- `numbers` is inferred to have the type `ArrayList<Integer>`.

The compiler uses the initializer to determine each variable's type.

## 5. `var` vs Explicit Type Declaration

| Feature | Explicit Type | `var` |
|---|---|---|
| Type declaration | Written by the programmer | Inferred by the compiler |
| Initialization | Not always required at declaration | Required |
| Type safety | Statically typed | Statically typed |
| Variable type | Fixed | Fixed |
| Supported since | Earlier Java versions | Java 10 |
| Readability | Makes the type explicit | Can reduce repetition |

Example:

```java
int age = 18;
```

The equivalent declaration using `var` is:

```java
var age = 18;
```

In both cases, `age` has the type `int`.

## 6. When Should You Use `var`?

Use `var` when the initializer makes the variable's type clear and the shorter declaration improves readability.

```java
var studentName = "Ananya";
var totalMarks = 450;
```

An explicit type may be clearer when the inferred type is not obvious from the expression.

The goal is not to replace every type declaration with `var`. Choose the form that makes your code easiest to understand.

## Conclusion

The `var` keyword simplifies local variable declarations through compile-time type inference. It reduces repetitive code while preserving Java's static type system. Understanding its rules helps you write concise and readable Java programs without losing type safety.

## Next Topic

Continue with [Naming Conventions in Java](10-Naming-Conventions.md) to learn how to name variables, methods, classes, and constants consistently.
