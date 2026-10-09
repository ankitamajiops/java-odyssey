# instanceof Operator in Java

## 1. Introduction

The `instanceof` operator in Java is used to check whether an object is an instance of a particular class, a subclass, or a class that implements a specified interface.

It returns a boolean value:

- `true` if the object is an instance of the specified type.
- `false` if it is not.

The `instanceof` operator is useful when working with objects, inheritance, and polymorphism.

## 2. Syntax

```java
object instanceof Type
```

Here:
- `object` is the object being checked.
- `Type` is the class, subclass, or interface being checked.

## 3. Basic Example

```java
public class Main {
    public static void main(String[] args) {
        String name = "Java";

        System.out.println(name instanceof String);
        System.out.println(name instanceof Object);
    }
}
```

**Output:**

```text
true
true
```

**Explanation:**

- `name instanceof String` returns `true` because `name` refers to a `String` object.
- `name instanceof Object` also returns `true` because `String` is a subclass of `Object`.

## 4. Example with Inheritance

```java
class Animal {
}

class Dog extends Animal {
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();

        System.out.println(dog instanceof Dog);
        System.out.println(dog instanceof Animal);
        System.out.println(dog instanceof Object);
    }
}
```

**Output:**

```text
true
true
true
```

**Explanation:**

- The object is a `Dog`, so the first condition is `true`.
- `Dog` extends `Animal`, so the object can also be treated as an `Animal`.
- Every Java class ultimately inherits from `Object`, so the third condition is also `true`.

## 5. Example with a False Result

```java
public class Main {
    public static void main(String[] args) {
        Object value = "Hello";

        System.out.println(value instanceof String);
        System.out.println(value instanceof Integer);
    }
}
```

**Output:**

```text
true
false
```

**Explanation:**

The actual object referenced by `value` is a `String`, not an `Integer`. Therefore, the second expression returns `false`.

## 6. Checking for null

In Java, using `instanceof` with `null` returns `false`.

```java
public class Main {
    public static void main(String[] args) {
        String name = null;

        System.out.println(name instanceof String);
    }
}
```

**Output:**

```text
false
```

## 7. Important Points

- The `instanceof` operator returns a boolean value.
- It can check an object's relationship with a class, subclass, or interface.
- It is commonly used with inheritance and polymorphism.
- If the reference is `null`, the result is always `false`.
- The check must be valid for the types involved; unrelated types may cause a compile-time error.
- `instanceof` checks the object's runtime type, not just the declared type of the reference variable.

## 8. Conclusion

The `instanceof` operator helps determine whether an object belongs to a particular type. It is especially useful when working with inheritance, polymorphism, and references to objects of different classes.

## 9. Next Topic

Continue learning Java operators in the next topic:

[**Operator Precedence and Associativity in Java**](11-Operator-Precedence-and-Associativity.md)
