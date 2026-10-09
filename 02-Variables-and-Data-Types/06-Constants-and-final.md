# Constants and the `final` Keyword in Java

In Java, variables are used to store values that a program can work with. Sometimes, however, a value should not be reassigned after it has been initialized.

Java provides the `final` keyword to prevent reassignment of a variable. A variable declared with `final` can be assigned only once.

Understanding constants and `final` helps make programs more reliable, readable, and easier to maintain.

## 1. What Is a Constant?

A constant is a value that is not intended to change during a particular part of a program's execution.

For example, the number of days in a week is always seven.

Instead of writing the number repeatedly, we can define a named constant.

```java
final int DAYS_IN_WEEK = 7;
```

Here:

- `final` prevents the variable from being reassigned.
- `int` is the data type.
- `DAYS_IN_WEEK` is the variable name.
- `7` is the assigned value.

In Java, constants are commonly declared using `final`.

## 2. The `final` Keyword

The `final` keyword can be used with variables, methods, and classes, but its effect depends on where it is used.

For variables, `final` means that the variable can be assigned only once.

### Example

```java
public class Main {
    public static void main(String[] args) {
        final int MAX_MARKS = 100;

        System.out.println(MAX_MARKS);
    }
}
```

Output:

```text
100
```

The program prints `100` because the variable has been assigned a value.

Trying to reassign it causes a compilation error:

```java
final int MAX_MARKS = 100;

// MAX_MARKS = 90; // Compilation error
```

Once assigned, a `final` variable cannot be assigned again.

## 3. Declaring and Initializing a `final` Variable

A `final` variable does not always need to be initialized in the same statement where it is declared. However, it must be assigned exactly once before it is read.

### Initialization at declaration

```java
final int age = 18;

System.out.println(age);
```

Output:

```text
18
```

### Initialization later

```java
final int marks;

marks = 95;

System.out.println(marks);
```

Output:

```text
95
```

This works because `marks` is assigned before it is used.

However, assigning a value to `marks` a second time would cause a compilation error.

## 4. Naming Conventions for Constants

Java commonly uses uppercase letters with underscores between words for constants.

Examples:

```java
final int MAX_MARKS = 100;
final double PI_APPROXIMATION = 3.14159;
final int DAYS_IN_WEEK = 7;
```

For ordinary variables, Java generally uses camelCase:

```java
int studentAge = 18;
double totalMarks = 450.0;
```

Using descriptive names helps make code easier to understand.

Note that uppercase naming is a convention, not a language requirement.

## 5. `final` with Primitive Variables

When a primitive variable is declared `final`, its value cannot be reassigned.

Example:

```java
public class Main {
    public static void main(String[] args) {
        final int number = 10;
        final double price = 99.5;
        final char grade = 'A';

        System.out.println(number);
        System.out.println(price);
        System.out.println(grade);
    }
}
```

Output:

```text
10
99.5
A
```

These variables cannot be assigned different values after their initial assignment.

## 6. `final` with Reference Variables

A reference variable declared `final` cannot be reassigned to refer to another object. However, if the object itself is mutable, its contents may still be changed.

Example:

```java
class Student {
    String name;
}

public class Main {
    public static void main(String[] args) {
        final Student student = new Student();

        student.name = "Ankita";

        System.out.println(student.name);
    }
}
```

Output:

```text
Ankita
```

This works because `final` prevents reassignment of the reference, not modification of the object's fields.

For example, this would cause a compilation error:

```java
final Student student = new Student();

// student = new Student(); // Compilation error
```

The reference `student` cannot be reassigned to another `Student` object.

## 7. The Difference Between `final` and Immutability

The terms `final` and immutable are related, but they do not mean the same thing.

- **`final` reference:** The reference cannot be reassigned.
- **Immutable object:** The object's state cannot be changed after creation.

For example, a `final` reference to a mutable object does not make that object immutable.

```java
final StringBuilder message = new StringBuilder("Hello");

message.append(" Java");

System.out.println(message);
```

Output:

```text
Hello Java
```

The example works because the reference remains the same, even though the contents of the `StringBuilder` object change.

By contrast, Java's `String` class is immutable.

## 8. `static final` Constants

A constant that belongs to a class rather than to individual objects is often declared using both `static` and `final`.

Example:

```java
class Circle {
    static final double PI = 3.14159;
}

public class Main {
    public static void main(String[] args) {
        System.out.println(Circle.PI);
    }
}
```

Output:

```text
3.14159
```

Here:

- `static` associates the field with the class.
- `final` prevents reassignment after initialization.
- `Circle.PI` accesses the constant using the class name.

A `static final` field is a common way to declare a class-level constant.

## 9. `final` with Methods and Classes

The `final` keyword can also be used with methods and classes.

### Final methods

A `final` method cannot be overridden by a subclass.

```java
class Parent {
    final void display() {
        System.out.println("Parent method");
    }
}
```

A subclass cannot provide an overriding implementation of this method.

### Final classes

A `final` class cannot be extended by another class.

```java
final class Vehicle {
}
```

A declaration such as `class Car extends Vehicle` would cause a compilation error.

These uses of `final` help control inheritance and method overriding in object-oriented programming.

## 10. Common Mistakes

### Mistake 1: Reassigning a `final` variable

Incorrect:

```java
final int age = 18;
age = 19;
```

The second assignment causes a compilation error.

### Mistake 2: Reading a `final` local variable before assigning it

Incorrect:

```java
final int marks;
System.out.println(marks);
```

The variable must be assigned before it is read.

### Mistake 3: Assuming a final reference makes an object immutable

```java
final StringBuilder text = new StringBuilder("Java");
text.append(" Programming");
```

This is valid because the object can change even though the reference cannot be reassigned.

## 11. Complete Java Program

```java
public class Main {
    public static void main(String[] args) {
        final int MAX_MARKS = 100;
        final int DAYS_IN_WEEK = 7;

        int marksObtained = 92;
        double percentage = (marksObtained * 100.0) / MAX_MARKS;

        System.out.println("Maximum marks: " + MAX_MARKS);
        System.out.println("Days in a week: " + DAYS_IN_WEEK);
        System.out.println("Marks obtained: " + marksObtained);
        System.out.println("Percentage: " + percentage);
    }
}
```

Output:

```text
Maximum marks: 100
Days in a week: 7
Marks obtained: 92
Percentage: 92.0
```

This program demonstrates how named constants can be reused in calculations without repeatedly writing unexplained numeric values.

## Conclusion

The `final` keyword prevents a variable from being reassigned after it has been assigned a value. It can also prevent method overriding and class inheritance when applied to methods and classes.

Using meaningful constant names makes programs easier to understand and maintain.

## Next Topic

Continue with [Type Conversion and Casting in Java](07-Type-Conversion-and-Casting.md).
