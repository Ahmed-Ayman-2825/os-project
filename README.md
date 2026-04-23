# MyShell Project - Operating Systems

## Team Information

Team Number: GN52

### Team Members

* Ahmed Ayman Khairy - 23011198
* Ahmed Mohamed Ahmed Fouad - 23010120
* Ahmed Emad AbdelTawab - 23012039
* Ahmed Mohamed Abdelwahab - 23010098
* Fares Waleed Hussein Balbaa - 22010187
* Abdelrahman Ahmed Abdelaziz - 23011108
* Gosam Hany Fouad - 23010095
* Ayman Salah Abdel Latif - 23010141
* Ibrahim Ramadan Al-Abd - 23011027
* ElSayed Mohamed Abdelrahman Othman - 23011227

---

## Project Overview

This project is a simple implementation of a Unix-like shell written in C.
The goal of the project is to understand how operating systems handle processes, commands, and user interaction.

The shell provides a command-line interface where the user can enter commands, and the system executes them similarly to basic Linux shells.

---

## How the Shell Works

The shell follows a simple loop:

1. Display a prompt (myShell>)
2. Read user input
3. Parse the command into arguments
4. Check for built-in commands
5. Execute the command using fork() and execvp()
6. Wait for the process (or run in background)

---

## Features Implemented

### 1. Command Execution

* Executes standard Linux commands such as ls, pwd, date
* Uses fork() to create a child process
* Uses execvp() to run commands

---

### 2. Built-in Commands

The shell handles some commands internally:

* cd → change directory using chdir()
* pwd → print current directory using getcwd()
* exit → terminate the shell
* history → display previous commands

---

### 3. Background Execution

* Commands ending with '&' run in the background
* The shell does not wait for them to finish
* The process ID (PID) is printed

---

### 4. Input/Output Redirection

* Output redirection using >
* Input redirection using <

Examples:
ls > output.txt
cat < output.txt

---

### 5. Pipes

* Supports single pipe using |
* Connects output of one command to input of another

Example:
ls | grep .c

---

### 6. Signal Handling

* Ctrl+C does not terminate the shell
* It only stops the running command
* Implemented using signal()

---

### 7. Error Handling

* Displays message for invalid commands
* Handles file opening errors
* Handles system call failures (fork, pipe)

---

## Team Contributions

* Ahmed Ayman Khairy
  Implemented the main shell loop, parsing logic, and command execution using fork() and execvp().

* Ahmed Mohamed Ahmed Fouad
  Developed built-in commands (cd, pwd, exit) and directory handling.

* Ahmed Emad AbdelTawab
  Implemented input/output redirection using file descriptors and dup2().

* Ahmed Mohamed Abdelwahab
  Developed the history feature for storing and displaying user commands.

* Fares Waleed Hussein Balbaa
  Implemented background process execution using '&'.

* Abdelrahman Ahmed Abdelaziz
  Handled process synchronization using wait() and waitpid().

* Gosam Hany Fouad
  Implemented error handling and validation of user commands.

* Ayman Salah Abdel Latif
  Implemented signal handling for Ctrl+C.

* Ibrahim Ramadan Al-Abd
  Created the Makefile and organized project compilation.

* ElSayed Mohamed Abdelrahman Othman
  Wrote documentation and tested all features to ensure correctness.

---

## How to Compile

make

---

## How to Run

./myShell

---

## Example Commands

ls
pwd
cd ..
history
sleep 5 &
ls > file.txt
cat < file.txt
ls | grep .c

---

## Notes

* system() is NOT used
* fork(), execvp(), wait() are used as required
* The project was tested on Ubuntu (WSL)
