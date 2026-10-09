# Types of Variables in Java

In Java, variables can be classified according to where they are declared and how they belong to a class or object.

The three important types of variables in this lesson are:

1. Local variables
2. Instance variables
3. Static variables

Understanding these types helps you manage data correctly and understand how Java objects and classes work.

## 1. Local Variables

A **local variable** is declared inside a method, constructor, or block of code.

It is used to store temporary information needed within that particular scope.

### Example

```java
public class Main {
    public static void main(String[] args) {
        int age = 18;
        String name = "Ankita";

        System.out.println(name);
        System.out.println(age);
    }
}
```

Output:

```text
Ankita
18
```

Here, `age` and `name` are local variables declared inside the `main()` method.

### Characteristics of Local Variables

- Declared inside a method, constructor, or block.
- Accessible only within their scope.
- Must be assigned a value before they are read.
- Do not automatically receive default values.
- Their scope ends when execution leaves the block in which they are declared.

### Local Variable Scope

```java
public class Main {
    public static void main(String[] args) {
        int number = 10;

        if (number > 0) {
            int result = 20;
            System.out.println(result);
        }

        System.out.println(number);
    }
}
```

Output:

```text
20
10
```

The variable `result` is declared inside the `if` block. It cannot be accessed outside that block.

## 2. Instance Variables

An **instance variable** is a non-static field declared inside a class but outside its methods, constructors, and blocks.

Each object of the class has its own instance fields.

### Example

```java
class Student {
    String name;
    int age;
}

public class Main {
    public static void main(String[] args) {
        Student student1 = new Student();
        student1.name = "Ankita";
        student1.age = 18;

        Student student2 = new Student();
        student2.name = "Riya";
        student2.age = 19;

        System.out.println(student1.name);
        System.out.println(student1.age);

        System.out.println(student2.name);
        System.out.println(student2.age);
    }
}
```

Output:

```text
Ankita
18
Riya
19
```

Here, `name` and `age` are instance variables.

Each `Student` object has its own copies of these fields. Changing one student's age does not automatically change the other student's age.

### Characteristics of Instance Variables

- Declared inside a class but outside methods and constructors.
- Belong to individual objects.
- Each object has its own instance-field values.
- Receive default values if they are not explicitly initialized.
- Can be accessed through an object reference, subject to access control.

## 3. Static Variables

A **static variable** is a class variable declared using the `static` keyword.

It belongs to the class rather than to each individual object. A class has one shared static field for that declaration, subject to class loading and initialization.

### Example

```java
class Student {
    String name;
    static String college = "ITER";
}

public class Main {
    public static void main(String[] args) {
        Student student1 = new Student();
        student1.name = "Ankita";

        Student student2 = new Student();
        student2.name = "Riya";

        System.out.println(student1.name);
        System.out.println(student2.name);

        System.out.println(Student.college);
    }
}
```

Output:

```text
Ankita
Riya
ITER
```

In this example:

- `name` is an instance variable because each student has a separate name.
- `college` is a static variable because the college value is shared by the class.

Static fields are best accessed using the class name, as in `Student.college`.

### Characteristics of Static Variables

- Declared using the `static` keyword.
- Associated with the class rather than individual instances.
- Shared among instances of the class.
- Receive default values if not explicitly initialized.
- Can be accessed through the class name, subject to access control.

## 4. Difference Between Local, Instance, and Static Variables

| Feature | Local variable | Instance variable | Static variable |
|---|---|---|---|
| Declaration | Inside a method, constructor, or block | Inside a class, outside methods and constructors | Inside a class with `static` |
| Belongs to | A particular scope or execution | An object | The class |
| Separate copy per object | Not applicable | Yes | No separate copy per object |
| Default value | No automatic default | Yes | Yes |
| Access | Within its scope | Through an object or within an allowed context | Through the class name or an allowed context |
| Typical use | Temporary calculations | Object-specific information | Data shared by the class |

## 5. Default Values

Instance and static fields receive default values when they are created and are not explicitly initialized.

For example:

```java
class Example {
    int number;
    boolean status;
    String name;

    static int count;
}

public class Main {
    public static void main(String[] args) {
        Example example = new Example();

        System.out.println(example.number);
        System.out.println(example.status);
        System.out.println(example.name);
        System.out.println(Example.count);
    }
}
```

Output:

```text
0
false
null
0
```

The default values shown here apply to fields. Local variables must be definitely assigned before they can be read.

## 6. Common Mistakes

### Mistake 1: Accessing a local variable outside its scope

```java
public class Main {
    public static void main(String[] args) {
        if (true) {
            int number = 10;
        }

        // System.out.println(number); // Compilation error
    }
}
```

The variable `number` is only accessible inside the `if` block.

### Mistake 2: Assuming instance variables are shared

```java
class Student {
    int marks;
}
```

Every `Student` object has its own `marks` field. Updating one object's field does not update another object's field.

### Mistake 3: Using an instance variable directly from a static method

```java
class Student {
    int age;

    static void displayAge() {
        // System.out.println(age); // Compilation error
    }
}
```

A static method does not have an implicit current object. It cannot directly access an instance field without an object reference.

A valid alternative is:

```java
class Student {
    int age;

    static void displayAge(Student student) {
        System.out.println(student.age);
    }
}
```

## 7. Complete Java Program

```java
class Student {
    String name;                  // Instance variable
    static String college = "ITER"; // Static variable

    void display() {
        int year = 1;             // Local variable

        System.out.println("Name: " + name);
        System.out.println("College: " + college);
        System.out.println("Year: " + year);
    }
}

public class Main {
    public static void main(String[] args) {
        Student student1 = new Student();
        student1.name = "Ankita";

        Student student2 = new Student();
        student2.name = "Riya";

        student1.display();
        student2.display();
    }
}
```

Output:

```text
Name: Ankita
College: ITER
Year: 1
Name: Riya
College: ITER
Year: 1
```

This program demonstrates all three types of variables:

- `name` is an instance variable.
- `college` is a static variable.
- `year` is a local variable inside the `display()` method.

## Conclusion

Local variables store temporary information within a scope, instance variables store object-specific data, and static variables store class-level data shared by instances.

Choosing the appropriate variable type helps keep Java programs organized and makes the relationship between classes and objects easier to understand.

## Next Topic

Continue with [Constants and the `final` Keyword](06-Constants-and-final.md).
