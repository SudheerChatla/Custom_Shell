
---

# Custom Shell – Unix-Like Shell Implementation

## 📌 Project Overview

This project is a custom shell written in C that emulates the behavior of Unix-like shells. It supports:

* Command execution (built-ins and external)
* Background and foreground process management
* Directory navigation
* Command piping and redirection
* Aliases and custom prompt
* Logging and command history
* Utilities like `reveal`, `seek`, `iman`, and `neonate`
* Signal handling for enhanced control

The shell is modular, with each feature implemented in its own source file for better organization and extensibility.

---

## 📁 Features and Source Files

### 1. **Command Execution**

Executes user commands, including built-in and external programs.

* `input.c`: Parses and executes commands.
* `io.c`: Handles I/O redirection.
* `pipe.c`: Manages command piping.

---

### 2. **Directory Navigation**

Custom `hop` command works similarly to `cd`.

* `hop.c`, `hop.h`: Handles navigation logic.

---

### 3. **Process Management**

Manages background and foreground jobs.

* `processes.c`: Implements `fg` and `bg` commands.
* `activites.c`: Tracks running/stopped jobs.
* `syscom.c`: Executes system-level commands.

---

### 4. **Logging**

Logs user commands with options to view, execute, or clear logs.

* `log.c`, `log.h`: Manages the log system.

---

### 5. **Piping**

Supports chaining commands using pipes (e.g., `ls | wc`).

* `pipe.c`, `pipe.h`: Implements pipe functionality.

---

### 6. **Aliases**

Define and manage command aliases.

* `aliases.c`, `aliases.h`: Provides alias functionality.

---

### 7. **File and Directory Search**

Searches for files and directories from the shell.

* `seek.c`, `seek.h`: Implements the `seek` utility.

---

### 8. **Process Information**

Displays detailed info about a process (similar to `ps`).

* `proclore.c`, `proclore.h`: Implements `proclore`.

---

### 9. **Signal Handling**

Handles signals like `SIGINT` (Ctrl+C) and `SIGTSTP` (Ctrl+Z).

* `signal.c`, `signal.h`: Provides robust signal handling.

---

### 10. **Custom Prompt**

Displays a user-friendly and informative prompt.

* `display.c`, `display.h`: Implements the shell prompt logic.

---

### 11. **Neonate Utility**

Monitors and prints the most recently created process ID periodically.

* `Neonate.c`, `Neonate.h`: Implements `neonate`.

---

### 12. **Reveal Utility**

Lists files and directories with options for hidden and detailed views.

* `reveal.c`, `reveal.h`: Implements `reveal`.

---

### 13. **iMan Utility**

Fetches manual pages for commands from [http://man.he.net](http://man.he.net).

* `iman.c`, `iman.h`: Implements `iman`.

---

## ⚙️ Implementation Details

### 🔁 Main Loop

* Located in `main.c`.
* Displays prompt and waits for user input in an infinite loop.
* Delegates parsing and execution to `input.c`.

### 🧠 Command Parsing

* Splits commands into tokens.
* Identifies built-ins, aliases, or system commands.
* Redirects to appropriate modules.

### 🧩 Modular Design

* Each feature has its own `.c` and `.h` files.
* Clean and extensible code structure.

### ❗ Error Handling

* Provides informative error messages for invalid input, permission errors, etc.

---

## 🚀 Getting Started

### 🛠️ Compile the Project

```bash
make
```

### ▶️ Run the Shell

```bash
./a.out
```

### 📥 Use the Shell

* Execute standard commands: `ls`, `echo`, `pwd`
* Use built-ins: `hop`, `log`, `seek`, `fg`, `bg`
* Define aliases in `myshrc.bashrc` (optional)

### 🧹 Clean Up

```bash
make clean
```

---

## 📚 Conclusion

This custom shell is a robust Unix-like terminal with modular components that provide insight into systems programming, process control, and shell utilities. It serves as a strong foundation for building advanced command-line environments or learning key OS-level concepts.
