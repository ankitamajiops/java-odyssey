# Relational Operators in Java

Relational operators compare two values and determine the relationship between them. The result of a relational comparison is always a Boolean value: `true` or `false`.

These operators are commonly used in `if` statements, loops, and other decision-making structures.

## 1. Types of Relational Operators

| Operator | Name | Meaning | Example |
|---|---|---|---|
| `<` | Less than | Checks whether the left value is smaller | `5 < 10` gives `true` |
| `>` | Greater than | Checks whether the left value is larger | `10 > 5` gives `true` |
| `<=` | Less than or equal to | Checks whether the left value is smaller than or equal to the right | `5 <= 5` gives `true` |
| `>=` | Greater than or equal to | Checks whether the left value is larger than or equal to the right | `10 >= 5` gives `true` |

Java also provides equality operators, `==` and `!=`, which are commonly studied alongside relational operators.

## 2. Less Than Operator (`<`)

The less than operator checks whether the left operand is smaller than the right operand.

```java
int a = 5;
int b = 10;

System.out.println(a < b);
System.out.println(b < a);
```

Output:

```text
true
false
```

The first comparison is true because `5` is less than `10`. The second is false because `10` is not less than `5`.

## 3. Greater Than Operator (`>`)

The greater than operator checks whether the left operand is larger than the right operand.

```java
int a = 15;
int b = 10;

System.out.println(a > b);
System.out.println(b > a);
```

Output:

```text
true
false
```

## 4. Less Than or Equal To Operator (`<=`)

The less than or equal to operator returns `true` when the left operand is smaller than or equal to the right operand.

```java
int a = 10;
int b = 10;

System.out.println(a <= b);
System.out.println(5 <= 10);
System.out.println(15 <= 10);
```

Output:

```text
true
true
false
```

Notice that `10 <= 10` is true because equality is included.

## 5. Greater Than or Equal To Operator (`>=`)

The greater than or equal to operator returns `true` when the left operand is larger than or equal to the right operand.

```java
int a = 20;
int b = 15;

System.out.println(a >= b);
System.out.println(10 >= 10);
System.out.println(5 >= 10);
```

Output:

```text
true
true
false
```

## 6. Equality Operators

Equality operators compare two operands for equality or inequality.

| Operator | Meaning | Example |
|---|---|---|
| `==` | Equal to | `5 == 5` gives `true` |
| `!=` | Not equal to | `5 != 10` gives `true` |

Example:

```java
int a = 10;
int b = 20;

System.out.println(a == b);
System.out.println(a != b);
```

Output:

```text
false
true
```

For primitive values, `==` checks whether the values are equal. For objects, `==` checks whether both references refer to the same object, rather than whether the objects have equivalent contents.

## 7. Using Relational Operators With Conditions

Relational operators are often used with `if-else` statements to make decisions.

```java
public class Main {
    public static void main(String[] args) {
        int marks = 75;

        if (marks >= 40) {
            System.out.println("Passed");
        } else {
            System.out.println("Failed");
        }
    }
}
```

Output:

```text
Passed
```

The condition `marks >= 40` evaluates to `true`, so the program prints `Passed`.

## 8. Comparing User-Defined Numeric Values

Relational operators can compare values stored in variables.

```java
public class Main {
    public static void main(String[] args) {
        int firstNumber = 25;
        int secondNumber = 30;

        System.out.println("First is smaller: " + (firstNumber < secondNumber));
        System.out.println("First is greater: " + (firstNumber > secondNumber));
        System.out.println("Values are equal: " + (firstNumber == secondNumber));
    }
}
```

Output:

```text
First is smaller: true
First is greater: false
Values are equal: false
```

Parentheses make it clear that each comparison should be evaluated before the result is joined to the output string.

## 9. Important Points

- Relational comparisons produce a Boolean result: `true` or `false`.
- Do not confuse `=` with `==`. The first assigns a value; the second compares values.
- The operators `<`, `>`, `<=`, and `>=` are used with numeric values and compatible character values, not directly with Boolean values or ordinary object references.
- Use parentheses when they make complex expressions easier to understand.
- Java does not support mathematical chaining such as `1 < x < 10`. Instead, use `x > 1 && x < 10`.

## Conclusion

Relational operators are essential for comparing values and controlling program flow. They help Java programs evaluate conditions and make decisions based on numerical relationships.

## Next Topic

Continue with [Logical Operators in Java](05-Logical-Operators.md) to learn how to combine and reverse Boolean conditions.
