# Java Compilation and Execution

> **From human-readable code to a running program — let's follow Java's journey!**

When you write a Java program, your computer cannot directly execute the source code as written. Java uses a compilation and execution process to turn your code into a running application.

Let's understand every step!

---

## 1. The Complete Java Execution Flow

```text
       Java Source Code
         Hello.java
              |
              v
     Java Compiler (javac)
              |
              v
        Java Bytecode
         Hello.class
              |
              v
      Class Loader + JVM
              |
              v
   Bytecode Verification
              |
              v
   Execution Engine
   (Interpreter + JIT)
              |
              v
      Program Output
```

**The key idea:** The compiler translates source code into bytecode, and the JVM executes that bytecode.

---

## 📝 2. Step One — Write the Source Code

Create a file named `Hello.java`.

```java
public class Hello {
    public static void main(String[] args) {
        System.out.println("Hello, Java Odyssey!");
    }
}
```

This is called **source code** because it is the code written by the programmer.

Java source files normally use the `.java` extension.

---

## 3. Step Two — Compile the Program

Open a terminal in the directory containing `Hello.java` and run:

```bash
javac Hello.java
```

The `javac` compiler checks and compiles the source code.

If compilation succeeds, it creates:

```text
Hello.class
```

The `.class` file contains **Java bytecode**, not ordinary Java source code and not necessarily native machine code.

### What if there is an error?

For example, if you miss a semicolon or use an invalid statement, the compiler may report a compilation error. Fix the error and compile again.

---

## 4. Step Three — Run the Program

In the same directory, run:

```bash
java Hello
```

Notice that you normally write `Hello`, **not** `Hello.class`.

The Java launcher starts the runtime, which loads the class and executes its bytecode.

Expected output:

```text
Hello, Java Odyssey!
```
---

## 5. Why Does Java Use Bytecode?

Java bytecode helps make Java platform-independent.

The same compiled class file can run on different operating systems when a compatible JVM and required libraries are available.

```text
              Hello.class
                   |
          +--------+--------+
          |        |        |
          v        v        v
       Windows   Linux     macOS
         JVM       JVM       JVM
```

The bytecode is generally the same; the JVM implementation handles execution on its particular platform.

This is the foundation of Java's famous principle:

**Write Once, Run Anywhere (WORA).**

---

## 6. What Happens Inside the JVM?

The JVM performs several important tasks.

### Class Loader

Loads classes needed by the program into the JVM.

### Bytecode Verifier

Checks bytecode for certain structural and safety constraints before execution.

### Execution Engine

Executes the bytecode. It can use:

* **Interpreter:** Executes bytecode instructions.
* **JIT compiler:** Compiles frequently executed code into native machine code at runtime to improve performance.

### Garbage Collector

Reclaims memory occupied by objects that are no longer reachable, when the JVM's garbage collector determines it is appropriate.

These components work together to run Java applications.

---

## 7. Why Does Java Use Both a Compiler and an Interpreter?

**The compiler (`javac`)** translates Java source code into bytecode before the program runs. It also detects many errors, such as syntax and type errors.

**The interpreter inside the JVM** can execute bytecode instructions at runtime. Modern JVMs also use JIT compilation to optimize frequently executed code.

Using bytecode allows Java to separate compilation from platform-specific execution.

---

## 8. Try It Yourself

Create `Sum.java`:

```java
public class Sum {
    public static void main(String[] args) {
        int a = 10;
        int b = 20;
        int sum = a + b;

        System.out.println("Sum = " + sum);
    }
}
```

Compile it:

```bash
javac Sum.java
```

Run it:

```bash
java Sum
```

Expected output:

```text
Sum = 30
```
---

**Coming next:** [Installing Java](05-Installing-Java.md)

---

*Part of Java Odyssey ☕ — Learn. Code. Understand. Repeat.*
