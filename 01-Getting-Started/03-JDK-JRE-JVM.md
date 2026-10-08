# JDK vs JRE vs JVM

> **Three names. Three different roles. One Java ecosystem.**

If you want to understand how Java programs are developed and executed, you need to understand the **JDK, JRE, and JVM**.

Let's break them down! 

---

## 1. What Is the JVM?

**JVM stands for Java Virtual Machine.**

The JVM is the runtime engine that executes Java bytecode.

When you compile a Java source file, the Java compiler produces bytecode in a `.class` file. The JVM loads and executes that bytecode.

### How it works

```text
HelloWorld.java
      |
      | javac
      v
HelloWorld.class
      |
      | JVM
      v
Program executes
```

### Remember

* The JVM executes Java bytecode.
* It handles runtime tasks such as memory management and garbage collection.
* JVM implementations are available for different operating systems and processor architectures.

**In simple words:** The JVM helps Java bytecode run on a particular system.

---

## 2. What Is the JRE?

**JRE stands for Java Runtime Environment.**

Traditionally, the JRE means the components needed to run Java applications, including the JVM and supporting runtime libraries.

```text
JRE
 |
 +-- JVM
 |
 +-- Runtime libraries and supporting components
```

**In simple words:** The JRE provides the environment for running Java applications.

**Modern Java note:** Since Java 11, Oracle's standard JDK distribution no longer includes a separate, general-purpose JRE image in the same way older Java distributions did. Other vendors and tools may package runtimes differently.

---

## 3. What Is the JDK?

**JDK stands for Java Development Kit.**

The JDK provides the tools developers need to develop Java programs, including the compiler and utilities, along with the runtime components.

Common tools include:

* `javac` — compiles Java source code into bytecode.
* `java` — launches Java applications.
* `javadoc` — generates API documentation from source comments.
* `jar` — creates and manages Java archive files.

### A simplified relationship

```text
JDK
 |
 +-- Development tools
 |     |
 |     +-- javac
 |     +-- javadoc
 |     +-- jar
 |
 +-- Runtime components
       |
       +-- JVM
       +-- Java libraries
```

**In simple words:** The JDK is what you install when you want to develop Java programs.

---

## 🔍 4. JDK vs JRE vs JVM

| Point                 | JDK                            | JRE                           | JVM                                    |
| --------------------- | ------------------------------ | ----------------------------- | -------------------------------------- |
| Full form             | Java Development Kit           | Java Runtime Environment      | Java Virtual Machine                   |
| Main role             | Develop Java programs          | Provide a runtime environment | Execute bytecode                       |
| Compiler included     | Yes, typically `javac`         | Traditionally no              | No                                     |
| Can run Java programs | Yes, through its runtime tools | Yes, in the traditional model | Executes bytecode as part of a runtime |
| Main purpose          | Development and execution      | Execution environment         | Bytecode execution                     |

---

## 5. Real-Life Analogy

Imagine you're making a movie:

* **JDK = Film studio:** It has the tools to create the movie.
* **JRE = Cinema setup:** It provides what's needed to show the finished movie.
* **JVM = Projector:** It executes the instructions that make the movie appear on screen.

The analogy isn't exact, but it helps you remember the different roles.

---

## 6. Try It Yourself

If you have installed a JDK, open your terminal or command prompt and run:

```bash
java -version
```

This displays information about the Java runtime launcher.

Then run:

```bash
javac -version
```

This displays the version of the Java compiler, if it is available on your PATH.

**What do the results tell you?**

* If `java` works, a Java runtime launcher is available.
* If `javac` works, the Java compiler is available.
* If `javac` is not recognized, you may need to install a JDK or configure your PATH.

---

**Coming next:** [Java Compilation and Execution](04-Java-Compilation-and-Execution.md)

---

*Part of Java Odyssey ☕ — Learn. Code. Understand. Repeat.*
