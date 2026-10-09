# Naming Conventions in Java

Naming conventions are standard rules for naming variables, methods, classes, constants, and other elements in a Java program.

Java does not require every naming convention to compile a program, but following them makes code easier to read, understand, maintain, and collaborate on.

## 1. Rules for Naming Identifiers

An *identifier* is the name given to a programming element, such as a variable, method, or class.

Java identifier rules include:

- An identifier can contain letters, digits, underscores (`_`), and dollar signs (`$`).
- An identifier cannot begin with a digit.
- Spaces are not allowed in identifiers.
- Java keywords, such as `class`, `int`, and `public`, cannot be used as identifiers.
- Java is case-sensitive, so `age`, `Age`, and `AGE` are different identifiers.
- Meaningful names are recommended to make code easier to understand.

Example:

```java
int studentAge = 18;
int totalMarks = 450;
```

Here, `studentAge` and `totalMarks` are valid and meaningful identifiers.

## 2. Variable Naming Convention

Variable names should generally use **camelCase**. The first word begins with a lowercase letter, and each subsequent word starts with an uppercase letter.

Examples:

```java
int studentAge = 18;
double accountBalance = 2500.50;
String firstName = "Ananya";
boolean isAvailable = true;
```

Avoid unclear names such as `x`, `a1`, or `data` when a more descriptive name is appropriate.

## 3. Method Naming Convention

Method names should generally use camelCase and usually begin with a verb describing the method's action.

Examples:

```java
void displayMessage() {
    System.out.println("Welcome to Java");
}

int calculateTotal(int a, int b) {
    return a + b;
}
```

Names such as `displayMessage()` and `calculateTotal()` help communicate what the methods do.

## 4. Class Naming Convention

Class names should use **PascalCase**. Each word begins with an uppercase letter, including the first word.

Examples:

```java
class StudentDetails {
}

class BankAccount {
}

class EmployeeRecord {
}
```

Class names usually represent objects, concepts, or entities.

## 5. Constant Naming Convention

Constants declared using `static final` are conventionally written in **UPPER_SNAKE_CASE**. Words are separated by underscores.

Example:

```java
static final double PI = 3.14159;
static final int MAX_ATTEMPTS = 3;
static final String COLLEGE_NAME = "ITER";
```

This style makes constants easy to distinguish from ordinary variables.

## 6. Package Naming Convention

Package names are generally written in lowercase letters. For larger projects, developers commonly use a reversed domain name as the beginning of the package name to help ensure uniqueness.

Examples:

```java
package com.example.student;
package org.company.project;
```

Avoid uppercase letters in package names unless a specific project convention requires otherwise.

## 7. Interface and Enum Naming Convention

Interface and enum type names generally follow PascalCase, just like class names.

Examples:

```java
interface Printable {
}

enum Day {
    MONDAY,
    TUESDAY,
    WEDNESDAY
}
```

Enum constants are conventionally written in uppercase with underscores when needed.

## 8. Complete Example

```java
public class StudentRecord {

    static final int PASS_MARKS = 40;

    public static void main(String[] args) {
        String studentName = "Ananya";
        int studentMarks = 85;

        boolean hasPassed = studentMarks >= PASS_MARKS;

        System.out.println("Student: " + studentName);
        System.out.println("Marks: " + studentMarks);
        System.out.println("Passed: " + hasPassed);
    }
}
```

Output:

```text
Student: Ananya
Marks: 85
Passed: true
```

In this example:

- `StudentRecord` follows PascalCase for a class.
- `PASS_MARKS` follows UPPER_SNAKE_CASE for a constant.
- `studentName`, `studentMarks`, and `hasPassed` follow camelCase for variables.
- `main` follows the conventional method naming style.

## Conclusion

Following Java naming conventions makes programs more readable, consistent, and professional. Although some naming styles are conventions rather than compiler-enforced rules, using them consistently is an important programming habit.

## Next Topic

Continue learning Java with [Operators in Java](../03-Operators/README.md)
