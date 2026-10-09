# Introduction to Variables in Java

A program becomes useful when it can store information, process it, and produce results. In Java, **variables** allow us to store and work with data while a program runs.

Understanding variables is one of the first steps toward mastering Java programming.

## 1. What Is a Variable?

A variable is a named storage location used to hold a value of a particular data type.

Think of a variable as a labeled container. The label identifies the variable, while the value is the information stored in it.

For example:

```java
int age = 18;
```

Here:

* `int` specifies the data type.
* `age` is the variable name.
* `18` is the value stored in the variable.
* `=` is the assignment operator used to assign the value.

The variable `age` stores an integer value.

## 2. Why Do We Need Variables?

Variables help us store information and reuse it throughout a program.

Consider a program that displays a student's age:

```java
public class Main {
    public static void main(String[] args) {
        int age = 18;

        System.out.println(age);
    }
}
```

Output:

```text
18
```

Instead of writing the number directly wherever it is needed, we can store it in a variable and use its name.

Variables are useful for:

* Storing user input.
* Performing calculations.
* Keeping track of values that change.
* Making programs easier to read and maintain.
* Reusing data without repeating the same literal values.

## 3. How to Declare a Variable

Declaring a variable means specifying its data type and name.

General syntax:

```java
dataType variableName;
```

Example:

```java
int marks;
double percentage;
char grade;
```

These statements declare three variables with different data types.

At this point, the variables have been declared but not explicitly assigned values.

A local variable in Java must be definitely assigned before it is read.

## 4. How to Initialize a Variable

Initialization means giving a variable its initial value.

Example:

```java
int marks = 95;
double percentage = 93.5;
char grade = 'A';
```

A variable can also be declared first and initialized later:

```java
int marks;
marks = 95;

System.out.println(marks);
```

Output:

```text
95
```

The first statement declares the variable, and the second assigns its value.

## 5. Changing a Variable's Value

A variable's value can be changed after initialization, provided the assignment is compatible with its data type.

Example:

```java
int score = 50;

System.out.println(score);

score = 75;

System.out.println(score);
```

Output:

```text
50
75
```

The first output displays the original value. The second displays the updated value.

This is called **reassignment**.

Notice that `int` is not written again when the existing variable is reassigned.

## 6. Variables with Different Data Types

Java provides different data types for different kinds of information.

```java
int age = 18;
double cgpa = 8.7;
char grade = 'A';
boolean isEnrolled = true;
String name = "Ankita";
```

| Data type | Example    | Purpose                  |
| --------- | ---------- | ------------------------ |
| `int`     | `18`       | Whole numbers            |
| `double`  | `8.7`      | Decimal numbers          |
| `char`    | `'A'`      | A single character       |
| `boolean` | `true`     | A true-or-false value    |
| `String`  | `"Ankita"` | A sequence of characters |

`String` is a reference type, not a primitive data type.

The detailed rules for each type will be covered in the upcoming lessons.

## 7. A Complete Java Program Using Variables

```java
public class Main {
    public static void main(String[] args) {
        String name = "Ankita";
        int age = 18;
        double cgpa = 8.7;

        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("CGPA: " + cgpa);

        age = 19;

        System.out.println("Updated age: " + age);
    }
}
```

Output:

```text
Name: Ankita
Age: 18
CGPA: 8.7
Updated age: 19
```

This program demonstrates how to declare variables, initialize them, display their values, and update a value.

The `+` operator joins text with variable values when used in these print statements.

## 8. Rules for Naming Variables

Java has rules that variable names must follow.

**Valid variable names:**

```java
int age;
int studentMarks;
double totalAmount;
String firstName;
int number2;
```

**Invalid variable names:**

```java
int 2number;       // Cannot start with a digit
int student marks; // Cannot contain a space
int class;         // Cannot use a Java keyword
```

Important rules:

* A variable name can contain letters, digits, underscores, and dollar signs.
* It cannot begin with a digit.
* It cannot contain spaces.
* It cannot be a Java keyword, such as `class` or `int`.
* Java variable names are case-sensitive. `age`, `Age`, and `AGE` are different names.

For readability, Java commonly uses **camelCase** for variable names. The first word starts with a lowercase letter, and each following word begins with an uppercase letter.

Example:

```java
int studentAge;
double totalMarks;
String collegeName;
```

## 9. Common Mistakes

### Using a variable before assigning a value

```java
int marks;
System.out.println(marks);
```

This causes a compilation error because a local variable must be assigned a value before it is read.

Correct version:

```java
int marks = 95;
System.out.println(marks);
```

### Assigning an incompatible value

```java
int age = "eighteen";
```

This causes a compilation error because `"eighteen"` is a `String`, not an integer.

Correct version:

```java
int age = 18;
```

### Declaring the same local variable twice in the same scope

```java
int age = 18;
int age = 19;
```

This causes a compilation error in the same scope.

Correct version:

```java
int age = 18;
age = 19;
```

## Conclusion

Variables are fundamental building blocks of Java programs. They allow us to store, access, and update information using meaningful names.

## Next Topic

Continue with [Variable Declaration and Initialization](02-Declaration-and-Initialization.md).
