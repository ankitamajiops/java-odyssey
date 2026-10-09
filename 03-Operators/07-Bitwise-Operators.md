# Bitwise Operators in Java

Bitwise operators perform operations on individual bits of integral values. They are useful for understanding binary numbers, manipulating flags, and working with low-level data.

In Java, bitwise operators can be used with integral types such as `byte`, `short`, `char`, `int`, and `long`. Smaller integral types are generally promoted to `int` when used in these expressions.

## 1. Binary Representation

Computers represent integer values using binary digits called bits. Each bit is either `0` or `1`.

For example, the decimal number `5` can be represented using four bits as:

```text
0101
```

The decimal number `3` is:

```text
0011
```

Bitwise operators compare or manipulate these binary representations.

## 2. Types of Bitwise Operators

| Operator | Name | Description |
|---|---|---|
| `&` | Bitwise AND | Produces `1` when both corresponding bits are `1` |
| `|` | Bitwise OR | Produces `1` when at least one corresponding bit is `1` |
| `^` | Bitwise XOR | Produces `1` when corresponding bits are different |
| `~` | Bitwise complement | Reverses every bit |
| `<<` | Left shift | Shifts bits to the left |
| `>>` | Signed right shift | Shifts bits to the right while preserving the sign |
| `>>>` | Unsigned right shift | Shifts bits to the right, filling the leftmost bits with zeros |

The shift operators are covered in more detail in the next topic.

## 3. Bitwise AND (`&`)

The bitwise AND operator produces `1` only when both corresponding bits are `1`.

| A | B | A & B |
|---|---|---|
| `0` | `0` | `0` |
| `0` | `1` | `0` |
| `1` | `0` | `0` |
| `1` | `1` | `1` |

Example:

```java
public class Main {
    public static void main(String[] args) {
        int a = 5;
        int b = 3;

        System.out.println(a & b);
    }
}
```

Output:

```text
1
```

Binary calculation:

```text
  0101
& 0011
------
  0001
```

The result is `0001`, which represents decimal `1`.

## 4. Bitwise OR (`|`)

The bitwise OR operator produces `1` when at least one of the corresponding bits is `1`.

| A | B | A \| B |
|---|---|---|
| `0` | `0` | `0` |
| `0` | `1` | `1` |
| `1` | `0` | `1` |
| `1` | `1` | `1` |

Example:

```java
int a = 5;
int b = 3;

System.out.println(a | b);
```

Output:

```text
7
```

Binary calculation:

```text
  0101
| 0011
------
  0111
```

The result is decimal `7`.

## 5. Bitwise XOR (`^`)

The bitwise XOR operator produces `1` when the corresponding bits are different and `0` when they are the same.

| A | B | A ^ B |
|---|---|---|
| `0` | `0` | `0` |
| `0` | `1` | `1` |
| `1` | `0` | `1` |
| `1` | `1` | `0` |

Example:

```java
int a = 5;
int b = 3;

System.out.println(a ^ b);
```

Output:

```text
6
```

Binary calculation:

```text
  0101
^ 0011
------
  0110
```

The result is decimal `6`.

## 6. Bitwise Complement (`~`)

The bitwise complement operator reverses every bit: `0` becomes `1`, and `1` becomes `0`.

In Java, an `int` uses 32 bits. For an `int` value `x`, the following relationship holds:

`~x == -x - 1`

Example:

```java
int number = 5;

System.out.println(~number);
```

Output:

```text
-6
```

The result is negative because Java uses two's complement representation for signed integer values.

## 7. Bitwise Operators With Negative Numbers

Java represents signed integers using two's complement. Therefore, bitwise operations on negative numbers operate on their fixed-width binary representations.

Example:

```java
int number = -1;

System.out.println(number & 7);
System.out.println(number | 0);
System.out.println(number ^ 0);
```

Output:

```text
7
-1
-1
```

These results follow the bit patterns used to represent signed integers.

## 8. Bitwise Operators vs Logical Operators

Bitwise and logical operators can look similar, but they serve different purposes.

| Bitwise Operator | Logical Operator | Main Difference |
|---|---|---|
| `&` | `&&` | Bitwise AND operates on bits; logical AND combines Boolean conditions |
| `|` | `||` | Bitwise OR operates on bits; logical OR combines Boolean conditions |
| `^` | No direct logical counterpart | For Boolean operands, `^` gives true when the operands differ |

Example using Boolean values:

```java
boolean a = true;
boolean b = false;

System.out.println(a & b);
System.out.println(a && b);
System.out.println(a ^ b);
```

Output:

```text
false
false
true
```

For Boolean operands, `&` and `|` evaluate both operands, whereas `&&` and `||` may skip the second operand through short-circuit evaluation.

## 9. Practical Example: Checking a Bit

Bitwise AND can check whether a particular bit is set.

```java
int number = 5;

if ((number & 1) != 0) {
    System.out.println("The number is odd");
} else {
    System.out.println("The number is even");
}
```

Output:

```text
The number is odd
```

The expression `number & 1` checks the least significant bit. For an integer, that bit is `1` when the number is odd and `0` when it is even.

## Conclusion

Bitwise operators manipulate individual bits in integral values. Understanding AND, OR, XOR, and complement provides a foundation for binary arithmetic, bit manipulation, and the shift operators used in Java.

## Next Topic

Continue with [Shift Operators in Java](08-Shift-Operators.md) to learn how Java shifts bits left and right.
