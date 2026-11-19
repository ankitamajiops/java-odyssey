# Parameters and Arguments in Java

## 1. Introduction

Methods in Java can receive input values to perform specific operations. These inputs make methods flexible and reusable.

Two important concepts related to method inputs are **parameters** and **arguments**.

Although these terms are closely related, they have different meanings.

## 2. What Are Parameters?

**Parameters** are variables declared inside the parentheses of a method definition. They receive values when the method is called.

Parameters act as local variables within the method.

### Example

```java
public class Main {

    static void greet(String name) {
        System.out.println("Hello, " + name);
    }

    public static void main(String[] args) {
        greet("Ankita");
    }
}
```

### Output

```text
Hello, Ankita
```

### Explanation

In the method definition:

```java
static void greet(String name)
```

- `String` is the parameter's data type.
- `name` is the parameter variable.
- The method receives a string value through this parameter.

## 3. What Are Arguments?

**Arguments** are the actual values or expressions supplied to a method when it is called.

### Example

```java
public class Main {

    static void displayAge(int age) {
        System.out.println("Age: " + age);
    }

    public static void main(String[] args) {
        displayAge(19);
    }
}
```

### Output

```text
Age: 19
```

Here:

- `age` is the parameter.
- `19` is the argument.
- The value `19` is passed to the method when `displayAge()` is called.

## 4. Difference Between Parameters and Arguments

| Parameters | Arguments |
|---|---|
| Variables declared in a method definition | Values or expressions supplied during a method call |
| Specify the input types expected by a method | Provide the actual input values |
| Receive values when the method is called | Are passed to the method |
| Example: `int number` | Example: `10` |

Consider:

```java
static void square(int number) {
    System.out.println(number * number);
}

public static void main(String[] args) {
    square(5);
}
```

In this example:

- `number` is the parameter.
- `5` is the argument.

## 5. Methods With Multiple Parameters

A method can accept more than one parameter.

Each parameter must have a declared data type, and parameters are separated by commas.

### Example

```java
public class Main {

    static void add(int a, int b) {
        int sum = a + b;
        System.out.println("Sum = " + sum);
    }

    public static void main(String[] args) {
        add(10, 20);
    }
}
```

### Output

```text
Sum = 30
```

### Explanation

- `int a` and `int b` are the two parameters.
- `10` and `20` are the corresponding arguments.
- The method adds both values and displays the result.

## 6. Passing Different Arguments to the Same Method

The same method can be called multiple times with different arguments.

### Example

```java
public class Main {

    static void displayNumber(int number) {
        System.out.println("Number: " + number);
    }

    public static void main(String[] args) {
        displayNumber(10);
        displayNumber(25);
        displayNumber(50);
    }
}
```

### Output

```text
Number: 10
Number: 25
Number: 50
```

The method definition remains unchanged, but the output changes according to the argument supplied during each call.

## 7. Passing Expressions as Arguments

Arguments do not have to be simple literal values. Java also allows expressions to be passed as arguments.

### Example

```java
public class Main {

    static void displaySum(int result) {
        System.out.println("Sum = " + result);
    }

    public static void main(String[] args) {
        displaySum(10 + 20);
    }
}
```

### Output

```text
Sum = 30
```

The expression `10 + 20` is evaluated, and its resulting value is passed to the method.

## 8. Different Data Types as Parameters

Methods can accept parameters of different data types, depending on their requirements.

### Example

```java
public class Main {

    static void displayDetails(String name, int age, double marks) {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Marks: " + marks);
    }

    public static void main(String[] args) {
        displayDetails("Ankita", 19, 92.5);
    }
}
```

### Output

```text
Name: Ankita
Age: 19
Marks: 92.5
```

The method accepts:

- A `String` parameter for the name.
- An `int` parameter for the age.
- A `double` parameter for the marks.

The arguments must be compatible with the corresponding parameter types.

## 9. Order of Arguments Matters

Arguments are matched with parameters according to their position in the method call.

### Example

```java
public class Main {

    static void display(int a, int b) {
        System.out.println("a = " + a);
        System.out.println("b = " + b);
    }

    public static void main(String[] args) {
        display(10, 20);
        display(20, 10);
    }
}
```

### Output

```text
a = 10
b = 20
a = 20
b = 10
```

The first argument is assigned to the first parameter, and the second argument is assigned to the second parameter.

Changing the order of arguments can change the behavior of a method.

## 10. Rules for Parameters and Arguments

1. The number of arguments must match the number of parameters in a method call, unless the method uses variable-length arguments.
2. Arguments must be compatible with their corresponding parameter types.
3. Parameters are separated by commas in the method definition.
4. Arguments are separated by commas in the method call.
5. The order of arguments matters for ordinary positional method calls.
6. Parameters behave as local variables inside the method.
7. A method can have no parameters or multiple parameters.

## 11. Common Mistakes

### Mistake 1: Passing the Wrong Number of Arguments

Incorrect:

```java
static void add(int a, int b) {
    System.out.println(a + b);
}

public static void main(String[] args) {
    add(10);
}
```

The method requires two arguments, but only one is provided.

Correct:

```java
add(10, 20);
```

### Mistake 2: Passing an Incompatible Data Type

Incorrect:

```java
static void display(int number) {
    System.out.println(number);
}

public static void main(String[] args) {
    display("Java");
}
```

The method expects an integer, but a string is supplied.

### Mistake 3: Forgetting to Declare Parameter Types

Incorrect:

```java
static void add(a, b) {
    System.out.println(a + b);
}
```

Correct:

```java
static void add(int a, int b) {
    System.out.println(a + b);
}
```

## 12. Best Practices

- Use meaningful parameter names.
- Choose appropriate data types for parameters.
- Pass arguments in the correct order.
- Avoid unnecessary parameters.
- Use parameters to make methods reusable with different inputs.
- Keep methods focused on specific tasks.

## Next Topic

Continue to [Return Statement and Return Types](05-Return-Statement-and-Return-Types.md) to understand how methods send calculated values back to the calling code.
