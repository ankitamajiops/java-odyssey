# Enhanced `for` Loop in Java

## 1. What Is an Enhanced `for` Loop?

The enhanced `for` loop, also called the **for-each loop**, provides a simple way to iterate through the elements of an array or an object that implements `Iterable`, such as an `ArrayList`.

Unlike a traditional `for` loop, it does not require you to manage an index manually.

It is especially useful when you want to read or process every element in a collection.

## 2. Syntax

```java
for (dataType variable : arrayOrCollection) {
    // Statements to execute
}
```

Here:

- `dataType` is the type of each element.
- `variable` stores the current element during an iteration.
- `arrayOrCollection` is the array or iterable collection being processed.
- The colon (`:`) means that the loop takes each element from the given array or collection in turn.

## 3. Example: Print Array Elements

```java
public class Main {
    public static void main(String[] args) {
        int[] numbers = {10, 20, 30, 40, 50};

        for (int number : numbers) {
            System.out.println(number);
        }
    }
}
```

Output:

```text
10
20
30
40
50
```

### Explanation

1. The array contains five integers.
2. The loop takes the first element, `10`, and assigns it to `number`.
3. It prints the current value.
4. It repeats the process for the remaining elements.
5. After processing the last element, the loop terminates.

You do not need to initialize an index, check an index condition, or increment an index yourself.

## 4. Example: Calculate the Sum of Array Elements

```java
public class Main {
    public static void main(String[] args) {
        int[] numbers = {10, 20, 30, 40, 50};
        int sum = 0;

        for (int number : numbers) {
            sum += number;
        }

        System.out.println("Sum = " + sum);
    }
}
```

Output:

```text
Sum = 150
```

### Explanation

The loop processes each element and adds it to `sum`.

| Current element | Calculation | Updated sum |
|---:|---|---:|
| 10 | `0 + 10` | 10 |
| 20 | `10 + 20` | 30 |
| 30 | `30 + 30` | 60 |
| 40 | `60 + 40` | 100 |
| 50 | `100 + 50` | 150 |

After all elements have been processed, the final sum is `150`.

## 5. Example: Find the Largest Element

```java
public class Main {
    public static void main(String[] args) {
        int[] numbers = {12, 45, 7, 89, 34};

        int largest = numbers[0];

        for (int number : numbers) {
            if (number > largest) {
                largest = number;
            }
        }

        System.out.println("Largest = " + largest);
    }
}
```

Output:

```text
Largest = 89
```

The variable `largest` stores the largest value found so far. Whenever the current element is greater than `largest`, the variable is updated.

This example assumes the array contains at least one element.

## 6. Enhanced `for` Loop with an `ArrayList`

The enhanced `for` loop can also iterate through an `ArrayList`.

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> languages = new ArrayList<>();

        languages.add("Java");
        languages.add("Python");
        languages.add("C++");

        for (String language : languages) {
            System.out.println(language);
        }
    }
}
```

Output:

```text
Java
Python
C++
```

The loop processes each string in the list without requiring an index.

## 7. Traditional `for` Loop vs Enhanced `for` Loop

| Feature | Traditional `for` | Enhanced `for` |
|---|---|---|
| Index access | Available when using an index | No direct index variable |
| Syntax | More control statements | Simpler syntax |
| Iterating through all elements | Suitable | Especially convenient |
| Processing elements in order | Yes | Yes |
| Skipping directly to a chosen index | Possible with an indexed array loop | Not directly supported |
| Updating array elements by index | Convenient | Not directly supported through the loop variable |

### Traditional `for` loop

```java
int[] numbers = {10, 20, 30};

for (int i = 0; i < numbers.length; i++) {
    System.out.println(numbers[i]);
}
```

### Enhanced `for` loop

```java
int[] numbers = {10, 20, 30};

for (int number : numbers) {
    System.out.println(number);
}
```

Both examples print the same output:

```text
10
20
30
```

Use a traditional `for` loop when you need an index. Use an enhanced `for` loop when you simply want to process each element.

## 8. Can You Modify Array Elements Using an Enhanced `for` Loop?

For primitive arrays, assigning a new value to the loop variable does not change the corresponding array element.

```java
public class Main {
    public static void main(String[] args) {
        int[] numbers = {1, 2, 3};

        for (int number : numbers) {
            number = number * 2;
        }

        for (int number : numbers) {
            System.out.println(number);
        }
    }
}
```

Output:

```text
1
2
3
```

The variable `number` receives a copy of each integer. Changing that local variable does not update the array.

To modify the actual array elements, use an indexed loop:

```java
public class Main {
    public static void main(String[] args) {
        int[] numbers = {1, 2, 3};

        for (int i = 0; i < numbers.length; i++) {
            numbers[i] *= 2;
        }

        for (int number : numbers) {
            System.out.println(number);
        }
    }
}
```

Output:

```text
2
4
6
```

## 9. Limitations of the Enhanced `for` Loop

The enhanced `for` loop is convenient, but it is not the best choice for every situation.

- It does not provide a built-in index variable.
- It is not suitable when you need to iterate backward by index.
- It does not directly let you replace primitive array elements through the loop variable.
- Modifying a collection structurally while iterating over it may cause a `ConcurrentModificationException` for many standard collection implementations.

When you need precise control over indices or collection updates, consider a traditional `for` loop or an appropriate iterator.

## 10. When Should You Use an Enhanced `for` Loop?

Use it when:

- You need to read every element in an array.
- You want to calculate a sum, count values, or find a maximum.
- You need to process every element of an `ArrayList` or another iterable collection.
- You do not need the element's index.

## Conclusion

The enhanced `for` loop simplifies iteration through arrays and iterable collections. It improves readability when every element needs to be processed, but a traditional `for` loop is more appropriate when you need index-based control or want to replace array elements.

## Next Topic

Continue with [Nested Loops](06-Nested-Loops.md).
