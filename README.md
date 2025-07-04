# 🐚 Simple Shell in C

A custom-built Unix-like command-line shell developed in C as part of a systems programming course at IIIT-Delhi. This shell supports basic command execution, piping, command history, and provides insights into process execution upon termination.

## 🧑‍💻 Tech Stack
Language: C
System Calls: fork(), execvp(), wait(), pipe()
OS: Linux/Unix

## 🚀 Features

- 🖥️ Command Parsing with arguments
- 🧵 Process creation using `fork()` and execution using `execvp()`
- 🔁 Infinite command loop with prompt
- 🔗 Pipe (`|`) support for multi-stage command execution
- 📜 Command history tracking
- ⏱️ Execution statistics: PID, timestamp, and duration
- ❌ Graceful exit with Ctrl+C

## ⚙️ How It Works

1. Displays a custom prompt to the user.
2. Accepts and parses user commands along with arguments.
3. Supports built-in commands and piping (`cat file | grep text | wc -l`).
4. Forks a child process to run the command using `execvp()`.
5. Stores command history for current session.
6. On termination (Ctrl+C), it prints:
   - Command history
   - Execution details for each command: PID, start time, execution time, etc.

## 🧾 Sample Commands Supported

```bash
ls -l
echo Hello, World!
cat file.txt | grep keyword | wc -l
sort file.txt | uniq
./helloword

## USAGE
gcc simple-shell.c -o simple-shell
./simple-shell

## Academic Refrence
This project was developed as part of the Operating Systems coursework under the guidance of Prof. Vivek Kumar at IIIT-Delhi.
