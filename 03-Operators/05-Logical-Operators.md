# Logical Operators in Java

Logical operators are used to combine Boolean conditions or reverse a Boolean result. They are especially useful in decision-making statements, loops, and expressions that involve multiple conditions.

Java provides three main logical operators: logical AND (`&&`), logical OR (`||`), and logical NOT (`!`).

## 1. Logical AND (`&&`)

The logical AND operator returns `true` only when **both conditions are true**.

| Condition 1 | Condition 2 | Result |
|---|---|---|
| `true` | `true` | `true` |
| `true` | `false` | `false` |
| `false` | `true` | `false` |
| `false` | `false` | `false` |

Example:

```java
int age = 20;
boolean hasID = true;

System.out.println(age >= 18 && hasID);
```

Output:

```text
true
```

Both conditions are true, so the complete expression evaluates to `true`.

### Short-Circuit Behavior

The `&&` operator uses short-circuit evaluation. If the first condition is `false`, Java does not evaluate the second condition because the complete expression must be false.

```java
int number = 5;

System.out.println(number > 10 && number < 20);
```

Output:

```text
false
```

Since `number > 10` is false, Java skips the second condition.

## 2. Logical OR (`||`)

The logical OR operator returns `true` when **at least one condition is true**. It returns `false` only when both conditions are false.

| Condition 1 | Condition 2 | Result |
|---|---|---|
| `true` | `true` | `true` |
| `true` | `false` | `true` |
| `false` | `true` | `true` |
| `false` | `false` | `false` |

Example:

```java
int age = 16;
boolean hasPermission = true;

System.out.println(age >= 18 || hasPermission);
```

Output:

```text
true
```

The first condition is false, but the second is true. Therefore, the complete expression evaluates to `true`.

### Short-Circuit Behavior

The `||` operator also uses short-circuit evaluation. If the first condition is `true`, Java skips the second condition because the complete expression is already true.

```java
int number = 15;

System.out.println(number > 10 || number < 0);
```

Output:

```text
true
```

Since the first condition is true, Java does not need to evaluate the second condition.

## 3. Logical NOT (`!`)

The logical NOT operator reverses a Boolean value. It changes `true` to `false` and `false` to `true`.

| Original Value | Result of `!` |
|---|---|
| `true` | `false` |
| `false` | `true` |

Example:

```java
boolean isRaining = false;

System.out.println(!isRaining);
```

Output:

```text
true
```

The value of `isRaining` remains `false`; the `!` operator reverses its value only within the expression.

## 4. Combining Multiple Conditions

Logical operators can be combined to evaluate more complex conditions.

```java
public class Main {
    public static void main(String[] args) {
        int marks = 85;
        boolean submittedAssignment = true;

        if (marks >= 40 && submittedAssignment) {
            System.out.println("Requirements satisfied");
        } else {
            System.out.println("Requirements not satisfied");
        }
    }
}
```

Output:

```text
Requirements satisfied
```

Both conditions are true, so the program executes the first branch.

## 5. Logical Operators vs Bitwise Operators

Java has both logical operators and bitwise operators. Although some symbols look similar, their behavior differs.

| Operator | Purpose |
|---|---|
| `&&` | Logical AND with short-circuit evaluation |
| `||` | Logical OR with short-circuit evaluation |
| `&` | Bitwise AND for integral values; also Boolean AND without short-circuiting |
| `|` | Bitwise OR for integral values; also Boolean OR without short-circuiting |
| `!` | Logical NOT for Boolean values |

For Boolean operands, `&` and `|` evaluate both operands, whereas `&&` and `||` may skip the second operand.

Example:

```java
int number = 5;

System.out.println(number > 10 && number++ > 0);
System.out.println(number);
```

Output:

```text
false
5
```

The first condition is false, so `number++` is not evaluated. Therefore, `number` remains `5`.

## 6. Practical Example

The following program checks whether a student satisfies two conditions.

```java
public class Main {
    public static void main(String[] args) {
        int marks = 75;
        boolean attendanceEligible = true;

        boolean eligible = marks >= 40 && attendanceEligible;

        System.out.println("Eligible: " + eligible);
    }
}
```

Output:

```text
Eligible: true
```

The student is eligible because the marks condition and the attendance condition are both true.

## Conclusion

Logical operators help Java programs combine conditions and make decisions. The AND operator requires both conditions to be true, the OR operator requires at least one condition to be true, and the NOT operator reverses a Boolean result.

Understanding short-circuit evaluation is also important because it affects which parts of an expression Java executes.

## Next Topic

Continue with [Assignment Operators in Java](06-Assignment-Operators.md) to learn how Java assigns and updates variable values.
