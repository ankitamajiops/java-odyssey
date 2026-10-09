# Shift Operators in Java

## 1. Introduction

Shift operators in Java are used to shift the bits of an integer value to the left or right.

They operate on integral types such as `byte`, `short`, `char`, `int`, and `long`. In most shift expressions, values of type `byte`, `short`, and `char` are promoted to `int` before the operation.

Java provides three shift operators:

- Left shift (`<<`)
- Signed right shift (`>>`)
- Unsigned right shift (`>>>`)

## 2. Left Shift Operator (`<<`)

The left shift operator moves the bits of a number to the left by the specified number of positions. The empty positions on the right are filled with zeros, and bits shifted beyond the left side are discarded.

### Example

```java
public class Main {
    public static void main(String[] args) {
        int number = 8;

        System.out.println(number << 1);
        System.out.println(number << 2);
    }
}
```

**Output:**

```text
16
32
```

**Explanation:**

The binary representation of `8` ends with `1000`.

- `8 << 1` shifts the bits one position to the left, producing `16`.
- `8 << 2` shifts the bits two positions to the left, producing `32`.

For positive values, left shifting by one position often has the same effect as multiplying by 2, provided the result does not overflow.

## 3. Signed Right Shift Operator (`>>`)

The signed right shift operator moves the bits to the right. The empty positions on the left are filled with copies of the original sign bit.

- For positive numbers, zeros are inserted on the left.
- For negative numbers, ones are inserted on the left.

### Example

```java
public class Main {
    public static void main(String[] args) {
        int number = 8;

        System.out.println(number >> 1);
        System.out.println(number >> 2);
    }
}
```

**Output:**

```text
4
2
```

**Explanation:**

- `8 >> 1` shifts the bits one position to the right, resulting in `4`.
- `8 >> 2` shifts the bits two positions to the right, resulting in `2`.

### Example with a Negative Number

```java
public class Main {
    public static void main(String[] args) {
        int number = -8;

        System.out.println(number >> 1);
    }
}
```

**Output:**

```text
-4
```

The sign bit is preserved, so the result remains negative.

## 4. Unsigned Right Shift Operator (`>>>`)

The unsigned right shift operator moves the bits to the right and fills the empty positions on the left with zeros, regardless of whether the original number is positive or negative.

### Example

```java
public class Main {
    public static void main(String[] args) {
        int positive = 8;
        int negative = -8;

        System.out.println(positive >>> 1);
        System.out.println(negative >>> 1);
    }
}
```

**Output:**

```text
4
2147483644
```

**Explanation:**

- `8 >>> 1` produces `4`.
- `-8 >>> 1` produces `2147483644` because Java's `int` type uses 32 bits. The unsigned shift inserts zeros on the left instead of preserving the negative sign.

This is why `>>` and `>>>` can produce very different results for negative numbers.

## 5. Difference Between Shift Operators

| Operator | Name | What happens on the left or right? |
|---|---|---|
| `<<` | Left shift | Moves bits left; fills right-side positions with zeros |
| `>>` | Signed right shift | Moves bits right; preserves the sign bit |
| `>>>` | Unsigned right shift | Moves bits right; fills left-side positions with zeros |

For positive numbers, `>>` and `>>>` generally produce the same result. Their difference becomes important for negative numbers.

## 6. Combined Example

```java
public class Main {
    public static void main(String[] args) {
        int number = 8;
        int negative = -8;

        System.out.println(number << 1);
        System.out.println(number >> 1);
        System.out.println(number >>> 1);
        System.out.println(negative >> 1);
        System.out.println(negative >>> 1);
    }
}
```

**Output:**

```text
16
4
4
-4
2147483644
```

## 7. Important Points

- Shift operators work on integral values, not floating-point types such as `float` and `double`.
- Java's `int` type has 32 bits, while `long` has 64 bits.
- The `<<` operator shifts bits to the left.
- The `>>` operator preserves the sign when shifting right.
- The `>>>` operator fills empty left-side positions with zeros.
- Bits shifted beyond the width of the value are discarded.
- Shift distances are handled according to the operand type: the lowest 5 bits of the distance are used for `int`, and the lowest 6 bits for `long`.

## 8. Conclusion

Shift operators are useful when working with binary data, bit manipulation, and certain low-level programming tasks. Understanding the difference between signed and unsigned right shifts is especially important when working with negative integers.

## 9. Next Topic

Continue learning Java operators in the next topic:

[**Ternary Operator in Java**](09-Ternary-Operator.md)
