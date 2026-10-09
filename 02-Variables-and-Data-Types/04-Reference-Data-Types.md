# Reference Data Types in Java

Java data types are broadly divided into primitive types and reference types. Primitive types store values such as integers and characters, while reference types are used to work with objects, arrays, and other non-primitive data.

Understanding reference types is important because they are widely used in object-oriented programming.

## 1. What Are Reference Data Types?

A reference type is a type whose variables can hold references to objects or arrays.

Examples include:

- `String`
- Arrays
- Classes created by programmers
- Interfaces
- Enums
- Records

Consider this example:

```java
String name = "Java";
```

Here, `String` is a reference type, `name` is the variable, and `"Java"` is the string value.

Unlike a primitive variable such as `int age = 18;`, a reference variable can refer to an object rather than directly storing the object's contents.

## 2. Primitive Types vs Reference Types

| Feature | Primitive types | Reference types |
|---|---|---|
| Examples | `int`, `char`, `boolean` | `String`, arrays, classes |
| Values | Store primitive values | Can refer to objects or arrays |
| Default field value | Depends on the type | `null` |
| Methods | Primitive values do not have instance methods | Objects can provide methods |
| Assignment | Copies the primitive value | Copies the reference value |
| Can be `null`? | No | Yes, if the type permits a null reference |

Java has eight primitive types: `byte`, `short`, `int`, `long`, `float`, `double`, `char`, and `boolean`.

All other types are reference types.

## 3. The String Type

`String` is a class in Java used to represent a sequence of characters.

Example:

```java
public class Main {
    public static void main(String[] args) {
        String name = "Ankita";
        String language = "Java";

        System.out.println(name);
        System.out.println(language);
    }
}
```

Output:

```text
Ankita
Java
```

Unlike a `char`, which represents one UTF-16 code unit, a `String` can contain multiple characters.

```java
char grade = 'A';
String subject = "Computer Science";
```

Character literals use single quotation marks, while string literals use double quotation marks.

### Strings are immutable

Strings are immutable, meaning their contents cannot be changed after the string object is created.

For example:

```java
String language = "Java";
language = language + " Programming";

System.out.println(language);
```

Output:

```text
Java Programming
```

This does not modify the original string object. The expression creates a new string value, and the variable is assigned a reference to that result.

## 4. Arrays

An array stores a fixed number of elements of the same component type.

Arrays are reference types in Java.

Example:

```java
public class Main {
    public static void main(String[] args) {
        int[] marks = {85, 90, 95};

        System.out.println(marks[0]);
        System.out.println(marks[1]);
        System.out.println(marks[2]);
    }
}
```

Output:

```text
85
90
95
```

In Java, array indexing starts at `0`.

Therefore:

- `marks[0]` accesses the first element.
- `marks[1]` accesses the second element.
- `marks[2]` accesses the third element.

An array has a fixed length after it is created.

You can access its length using the `length` field:

```java
int[] numbers = {10, 20, 30};

System.out.println(numbers.length);
```

Output:

```text
3
```

## 5. Classes and Objects

A class is a blueprint for creating objects. An object is an instance of a class.

Variables whose types are classes are reference variables.

Example:

```java
class Student {
    String name;
    int age;
}

public class Main {
    public static void main(String[] args) {
        Student student = new Student();

        student.name = "Ankita";
        student.age = 18;

        System.out.println(student.name);
        System.out.println(student.age);
    }
}
```

Output:

```text
Ankita
18
```

In this example:

- `Student` is a class.
- `student` is a reference variable.
- `new Student()` creates a new `Student` object.
- `name` and `age` are fields of the object.

The reference variable allows the program to access the object's fields.

## 6. The null Value

Reference variables can hold `null`, which means they do not currently refer to an object or array.

Example:

```java
String name = null;

System.out.println(name);
```

Output:

```text
null
```

However, attempting to call an instance method through a null reference causes a `NullPointerException`.

```java
String name = null;

// This causes a NullPointerException:
System.out.println(name.length());
```

Before using a reference, ensure that it refers to a valid object when the operation requires one.

For example:

```java
String name = null;

if (name != null) {
    System.out.println(name.length());
}
```

This avoids calling `length()` when `name` is `null`.

## 7. Reference Assignment

When one reference variable is assigned to another, the reference value is copied. Both variables can then refer to the same object.

Example:

```java
class Box {
    int value;
}

public class Main {
    public static void main(String[] args) {
        Box first = new Box();
        first.value = 10;

        Box second = first;
        second.value = 20;

        System.out.println(first.value);
        System.out.println(second.value);
    }
}
```

Output:

```text
20
20
```

Both `first` and `second` refer to the same `Box` object. Changing the object's `value` through either reference is visible through the other.

This is an important difference between assigning primitive values and assigning object references.

## 8. Default Values of Reference Fields

Reference fields receive `null` as their default value when they are not explicitly initialized.

Example:

```java
class Student {
    String name;
    int[] marks;
}

public class Main {
    public static void main(String[] args) {
        Student student = new Student();

        System.out.println(student.name);
        System.out.println(student.marks);
    }
}
```

Output:

```text
null
null
```

The `name` and `marks` fields are reference fields, so both initially contain `null`.

Local reference variables are different: they must be assigned before they can be read.

## 9. Common Mistakes

### Mistake 1: Calling a method through null

Incorrect:

```java
String name = null;
System.out.println(name.length());
```

This causes a `NullPointerException`.

### Mistake 2: Using an array index that does not exist

Incorrect:

```java
int[] numbers = {10, 20, 30};
System.out.println(numbers[3]);
```

This causes an `ArrayIndexOutOfBoundsException`, because valid indexes are `0`, `1`, and `2`.

### Mistake 3: Confusing a reference variable with the object

```java
Student first = new Student();
Student second = first;
```

This does not create two objects. It creates one object and two references to it.

To create a separate object, use another `new` expression:

```java
Student first = new Student();
Student second = new Student();
```

## 10. Complete Java Program

```java
class Student {
    String name;
    int age;
}

public class Main {
    public static void main(String[] args) {
        String language = "Java";
        int[] marks = {85, 90, 95};

        Student student = new Student();
        student.name = "Ankita";
        student.age = 18;

        System.out.println("Language: " + language);
        System.out.println("First mark: " + marks[0]);
        System.out.println("Student: " + student.name);
        System.out.println("Age: " + student.age);
        System.out.println("Number of marks: " + marks.length);
    }
}
```

Output:

```text
Language: Java
First mark: 85
Student: Ankita
Age: 18
Number of marks: 3
```

This program demonstrates three reference types: `String`, an integer array, and a user-defined `Student` class.

## Conclusion

Reference types allow Java programs to work with strings, arrays, objects, and many other structures. A reference variable can refer to an object or array, or hold `null`.

## Next Topic

Continue with [Local, Instance, and Static Variables](05-Types-of-Variables.md).
