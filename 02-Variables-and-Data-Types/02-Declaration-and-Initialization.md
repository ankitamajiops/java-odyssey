# Variable Declaration and Initialization in Java

In Java, variables are used to store data. Before using a variable, we need to understand how to declare it, assign a value to it, and initialize it.

These concepts are closely related, but each has a different meaning.

## 1. Variable Declaration

**Variable declaration** means specifying a variable's data type and name.

### Syntax

```java
dataType variableName;
```

### Example

```java
int age;
double percentage;
char grade;
```

In these statements:

- `int`, `double`, and `char` are data types.
- `age`, `percentage`, and `grade` are variable names.

These statements declare the variables but do not explicitly assign values to them.

A local variable must be assigned a value before it can be read.

## 2. Variable Initialization

**Initialization** means giving a variable its initial value.

### Example

```java
int age = 18;
double percentage = 93.5;
char grade = 'A';
```

Here, each variable is declared and initialized in the same statement.

For example:

```java
int age = 18;
```

- `int` specifies the data type.
- `age` is the variable name.
- `=` is the assignment operator.
- `18` is the initial value.

## 3. Declaration and Initialization Separately

Java also allows us to declare a variable first and assign its initial value later.

```java
int marks;

marks = 95;

System.out.println(marks);
```

Output:

```text
95
```

The first statement declares `marks`. The second statement assigns its initial value.

The variable must receive a value before it is used.

## 4. Assignment After Initialization

Once a variable has been initialized, we can assign a new value to it.

```java
int score = 50;

System.out.println(score);

score = 80;

System.out.println(score);
```

Output:

```text
50
80
```

The first output displays the original value. The second displays the updated value.

This process is called **reassignment**.

Notice that we do not write `int` again when changing the value of an existing variable.

## 5. Understanding the Assignment Operator

The `=` symbol is called the **assignment operator** in Java.

It assigns the value on the right-hand side to the variable on the left-hand side.

```java
int number = 10;
number = 25;
```

After the second statement, `number` stores `25`.

Assignment can also involve calculations:

```java
int a = 10;
int b = 5;

int sum = a + b;

System.out.println(sum);
```

Output:

```text
15
```

The expression `a + b` is evaluated, and the result is assigned to `sum`.

## 6. Multiple Variable Declarations

Java allows multiple variables of the same data type to be declared in one statement.

```java
int a, b, c;
```

They can also be initialized together:

```java
int a = 10, b = 20, c = 30;
```

However, declaring variables on separate lines can sometimes make a program easier to read.

For example:

```java
int studentAge = 18;
int totalMarks = 450;
int subjectCount = 5;
```

Choose a style that keeps your code clear and understandable.

## 7. Reassigning Values Using Calculations

A variable's existing value can be used to calculate its next value.

```java
int number = 10;

number = number + 5;

System.out.println(number);
```

Output:

```text
15
```

The expression on the right is evaluated using the old value of `number`. The result is then assigned back to `number`.

Java also provides a shorthand assignment operator:

```java
int number = 10;

number += 5;

System.out.println(number);
```

Output:

```text
15
```

The statement `number += 5;` adds `5` to the current value of `number` and stores the result back in the same variable.

## 8. Declaration and Initialization of Local Variables

Consider the following program:

```java
public class Main {
    public static void main(String[] args) {
        int age;
        age = 18;

        System.out.println(age);
    }
}
```

Output:

```text
18
```

This program works because `age` receives a value before it is printed.

Now consider this example:

```java
public class Main {
    public static void main(String[] args) {
        int age;

        System.out.println(age);
    }
}
```

This program produces a compilation error because the local variable `age` has not been assigned a value before being read.

Unlike local variables, instance and static fields receive default values when they are not explicitly initialized. These differences will be covered in the lesson on types of variables.

## 9. Common Mistakes

### Mistake 1: Using an uninitialized local variable

Incorrect:

```java
int marks;
System.out.println(marks);
```

Correct:

```java
int marks = 95;
System.out.println(marks);
```

### Mistake 2: Declaring the same variable twice in the same scope

Incorrect:

```java
int age = 18;
int age = 19;
```

Correct:

```java
int age = 18;
age = 19;
```

### Mistake 3: Assigning a value of an incompatible type

Incorrect:

```java
int age = "eighteen";
```

Correct:

```java
int age = 18;
```

The variable's data type determines which values can be assigned to it.

## 10. Complete Java Program

```java
public class Main {
    public static void main(String[] args) {
        int marks;
        marks = 75;

        System.out.println("Initial marks: " + marks);

        marks = 90;

        System.out.println("Updated marks: " + marks);

        marks += 5;

        System.out.println("Final marks: " + marks);
    }
}
```

Output:

```text
Initial marks: 75
Updated marks: 90
Final marks: 95
```

This program demonstrates declaration, initialization through assignment, reassignment, and shorthand assignment.

## Conclusion

Variable declaration specifies the data type and name of a variable. Initialization gives it its initial value, while reassignment changes its value later.

## Next Topic

Continue with [Primitive Data Types in Java](03-Primitive-Data-Types.md).
