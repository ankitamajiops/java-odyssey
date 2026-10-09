# Assignment Operators in Java

Assignment operators are used to assign values to variables or update their existing values. They are commonly used in calculations, counters, loops, and many other Java programs.

## 1. Simple Assignment Operator (`=`)

The simple assignment operator assigns the value on the right to the variable on the left.

```java
int number = 10;
System.out.println(number);
```

Output:

```text
10
```

Here, the value `10` is assigned to the variable `number`.

## 2. Compound Assignment Operators

Compound assignment operators combine an operation with assignment. They provide a shorter way to update a variable.

| Operator | Example | Equivalent for an `int` variable |
|---|---|---|
| `+=` | `x += 5` | `x = x + 5` |
| `-=` | `x -= 5` | `x = x - 5` |
| `*=` | `x *= 5` | `x = x * 5` |
| `/=` | `x /= 5` | `x = x / 5` |
| `%=` | `x %= 5` | `x = x % 5` |

### Addition Assignment (`+=`)

Adds a value to the variable and assigns the result back to it.

```java
int number = 10;
number += 5;

System.out.println(number);
```

Output:

```text
15
```

### Subtraction Assignment (`-=`)

Subtracts a value from the variable and stores the result.

```java
int number = 10;
number -= 3;

System.out.println(number);
```

Output:

```text
7
```

### Multiplication Assignment (`*=`)

Multiplies the variable by a value and stores the result.

```java
int number = 6;
number *= 4;

System.out.println(number);
```

Output:

```text
24
```

### Division Assignment (`/=`)

Divides the variable by a value and assigns the quotient back to it.

```java
int number = 20;
number /= 4;

System.out.println(number);
```

Output:

```text
5
```

When both operands are integers, integer division rules apply.

### Remainder Assignment (`%=`)

Calculates the remainder and assigns it back to the variable.

```java
int number = 17;
number %= 5;

System.out.println(number);
```

Output:

```text
2
```

## 3. Bitwise Assignment Operators

Java also provides compound assignment operators for bitwise and shift operations.

| Operator | Example | Meaning |
|---|---|---|
| `&=` | `x &= y` | Bitwise AND, then assignment |
| `|=` | `x |= y` | Bitwise OR, then assignment |
| `^=` | `x ^= y` | Bitwise XOR, then assignment |
| `<<=` | `x <<= 2` | Left shift, then assignment |
| `>>=` | `x >>= 2` | Signed right shift, then assignment |
| `>>>=` | `x >>>= 2` | Unsigned right shift, then assignment |

Example:

```java
int number = 12;
number &= 10;

System.out.println(number);
```

Output:

```text
8
```

In binary, `12` is `1100` and `10` is `1010`. Applying bitwise AND gives `1000`, which is `8`.

These operators are useful when working with binary data and low-level operations.

## 4. Assignment Operators and Data Types

Compound assignment can perform an implicit conversion that a corresponding ordinary assignment would not allow.

Example:

```java
byte number = 10;
number += 5;

System.out.println(number);
```

Output:

```text
15
```

This works because compound assignment includes an implicit conversion back to the variable's type.

However, the following code does not compile:

```java
byte number = 10;
// number = number + 5;
```

The expression `number + 5` is evaluated as an `int`, so assigning it directly to a `byte` requires an explicit cast.

```java
byte number = 10;
number = (byte) (number + 5);

System.out.println(number);
```

Output:

```text
15
```

Be careful: explicit narrowing conversions can lose information if the result is outside the target type's range.

## 5. Complete Example

```java
public class Main {
    public static void main(String[] args) {
        int number = 20;

        number += 10;
        System.out.println("After += : " + number);

        number -= 5;
        System.out.println("After -= : " + number);

        number *= 2;
        System.out.println("After *= : " + number);

        number /= 5;
        System.out.println("After /= : " + number);

        number %= 3;
        System.out.println("After %= : " + number);
    }
}
```

Output:

```text
After += : 30
After -= : 25
After *= : 50
After /= : 10
After %= : 1
```

Each statement updates the same variable, `number`, using a different compound assignment operator.

## Conclusion

Assignment operators are fundamental to Java programming. The simple assignment operator stores a value, while compound assignment operators update variables through arithmetic, bitwise, or shift operations. Understanding them helps make code concise and easier to maintain.

## Next Topic

Continue with [Bitwise Operators in Java](07-Bitwise-Operators.md) to learn how Java performs operations on individual bits.
