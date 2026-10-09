# Unary Operators in Java

Unary operators are operators that work with a single operand. They are used to increase or decrease a value, change its sign, or reverse a Boolean condition.

Unary operators are commonly used in loops, calculations, conditional statements, and other Java programs.

## 1. Types of Unary Operators

| Operator | Name | Purpose |
|---|---|---|
| `+` | Unary plus | Indicates a positive numeric value |
| `-` | Unary minus | Reverses the sign of a numeric value |
| `++` | Increment | Increases a variable's value by one |
| `--` | Decrement | Decreases a variable's value by one |
| `!` | Logical complement | Reverses a Boolean value |
| `~` | Bitwise complement | Reverses each bit of an integer |

## 2. Unary Plus (`+`)

The unary plus operator indicates a positive numeric value. It generally does not change the value.

```java
int number = 10;
int result = +number;

System.out.println(result);
```

Output:

```text
10
```

## 3. Unary Minus (`-`)

The unary minus operator reverses the sign of a numeric value.

```java
int number = 10;
int result = -number;

System.out.println(result);
```

Output:

```text
-10
```

The original variable `number` remains `10`. The negative value is stored in `result`.

## 4. Increment Operator (`++`)

The increment operator increases a variable's value by one.

Java provides two forms of increment:

- **Pre-increment (`++x`):** Increments the variable first, then produces the updated value.
- **Post-increment (`x++`):** Produces the current value first, then increments the variable.

### Pre-Increment

```java
int x = 5;
int result = ++x;

System.out.println("x = " + x);
System.out.println("result = " + result);
```

Output:

```text
x = 6
result = 6
```

The variable is incremented before its value is used in the assignment.

### Post-Increment

```java
int x = 5;
int result = x++;

System.out.println("x = " + x);
System.out.println("result = " + result);
```

Output:

```text
x = 6
result = 5
```

The original value is assigned to `result` first. Then `x` is incremented.

## 5. Decrement Operator (`--`)

The decrement operator decreases a variable's value by one.

It also has pre-decrement and post-decrement forms.

### Pre-Decrement

```java
int x = 5;
int result = --x;

System.out.println("x = " + x);
System.out.println("result = " + result);
```

Output:

```text
x = 4
result = 4
```

The variable is decremented before its value is used.

### Post-Decrement

```java
int x = 5;
int result = x--;

System.out.println("x = " + x);
System.out.println("result = " + result);
```

Output:

```text
x = 4
result = 5
```

The original value is assigned to `result` before `x` is decremented.

## 6. Logical Complement (`!`)

The logical complement operator reverses a Boolean value.

- `true` becomes `false`.
- `false` becomes `true`.

Example:

```java
boolean isJavaEasy = true;

System.out.println(!isJavaEasy);
```

Output:

```text
false
```

It is also useful for reversing conditions.

```java
int age = 16;
boolean isAdult = age >= 18;

System.out.println(!isAdult);
```

Output:

```text
true
```

Because `age >= 18` is false, `isAdult` is false, and `!isAdult` is true.

## 7. Bitwise Complement (`~`)

The bitwise complement operator reverses every bit in an integer's binary representation.

For Java's 32-bit `int` type, this operation follows the relationship:

`~x` is equal to `-x - 1`.

Example:

```java
int number = 5;

System.out.println(~number);
```

Output:

```text
-6
```

For a 32-bit integer, `5` is represented in binary as:

```text
00000000 00000000 00000000 00000101
```

Applying `~` reverses every bit. The resulting bit pattern represents `-6` using two's complement.

## 8. Complete Example

```java
public class Main {
    public static void main(String[] args) {
        int number = 5;
        boolean isActive = true;

        System.out.println("Unary plus: " + (+number));
        System.out.println("Unary minus: " + (-number));

        System.out.println("Pre-increment: " + (++number));
        System.out.println("Post-increment: " + (number++));
        System.out.println("Current number: " + number);

        System.out.println("Logical complement: " + (!isActive));
        System.out.println("Bitwise complement: " + (~number));
    }
}
```

Output:

```text
Unary plus: 5
Unary minus: -5
Pre-increment: 6
Post-increment: 6
Current number: 7
Logical complement: false
Bitwise complement: -8
```

The output demonstrates how unary operators behave when applied to numeric and Boolean values.

## Conclusion

Unary operators perform operations on a single operand. Understanding increment, decrement, unary minus, logical complement, and bitwise complement is important for writing clear Java expressions and understanding how values change during program execution.

## Next Topic

Continue with [Relational Operators in Java](04-Relational-Operators.md) to learn how Java compares values.
