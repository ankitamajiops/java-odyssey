# Installing Java — Set Up Your Coding Environment

> **Before you write your first Java program, prepare your computer for the journey.** 

This guide explains how to install a Java Development Kit (JDK), verify your installation, and prepare to compile and run Java programs!

## 1. What Do You Need?

You need:

* A computer running Windows, macOS, or Linux.
* A **JDK (Java Development Kit)** to compile and run Java programs.
* A code editor, such as Visual Studio Code, or another Java IDE.

---

## 2. Download a JDK

You can download a JDK from a trusted provider:

* [Eclipse Temurin — JDK downloads](https://adoptium.net/)
* [Oracle Java downloads](https://www.oracle.com/java/technologies/downloads/)

For a new learning project, choose a currently supported **Long-Term Support (LTS)** version, such as Java 25, if your tools and coursework support it. Java 21 is another widely used LTS version.

Choose the download that matches your operating system and processor architecture.

---

## 3. Install Java on Windows

### Step 1 — Download the installer

1. Open the [Eclipse Temurin website](https://adoptium.net/).
2. Select a suitable LTS JDK version.
3. Choose Windows and the appropriate architecture, usually x64 for many Windows laptops.
4. Download the installer.

### Step 2 — Run the installer

1. Open the downloaded installer.
2. Follow the installation wizard.
3. If the installer offers options to add Java to `PATH` or set `JAVA_HOME`, enable them if appropriate.
4. Complete the installation.

The exact installer options can differ between JDK providers.

### Step 3 — Open a terminal

Open **PowerShell** or **Command Prompt**.

You can search for PowerShell in the Windows Start menu.

### Step 4 — Verify the installation

Run:

```powershell
java -version
```

Then run:

```powershell
javac -version
```

Both commands should display version information if the runtime launcher and compiler are installed and available on your `PATH`.

Example output format:

```text
java version "25..."
javac 25...
```

The exact version and output wording may differ.

---

## 4. Install Java on macOS

1. Download a macOS JDK installer from a trusted provider.
2. Choose the correct architecture for your Mac.
3. Open the installer and follow its instructions.
4. Open the Terminal application.
5. Run:

```bash
java -version
javac -version
```

If both commands display version information, the corresponding Java tools are available.

---

## 5. Install Java on Linux

Installation commands depend on your Linux distribution.

For Ubuntu or Debian, you can install a JDK using the package manager. For example:

```bash
sudo apt update
sudo apt install openjdk-21-jdk
```

This example installs the Java 21 JDK when the package is available in your configured repositories.

Verify it:

```bash
java -version
javac -version
```

Other Linux distributions may use different package managers and package names.

---

## 6. Test Your Installation

Let's make sure your setup works!

Create a file named `Hello.java` containing:

```java
public class Hello {
    public static void main(String[] args) {
        System.out.println("My Java journey begins!");
    }
}
```

Open a terminal in the folder where you saved the file.

Compile it:

```bash
javac Hello.java
```

Run it:

```bash
java Hello
```

Expected output:

```text
My Java journey begins!
```

If you see the message, your first Java setup test has succeeded!

---

**Coming next:** [Your First Java Program](06-First-Java-Program.md)

---

*Part of Java Odyssey ☕ — Learn. Code. Understand. Repeat.*
