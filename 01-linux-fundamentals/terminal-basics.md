# Linux Terminal Basics

## Introduction

The Linux terminal is a command-line interface (CLI) that allows users to interact with the operating system by entering commands.

Instead of using a graphical interface, users can perform tasks such as managing files, installing software, configuring networks, and monitoring system resources through the terminal.

## What is a Shell?

A shell is a program that accepts commands from users and passes them to the operating system for execution.

Popular Linux shells include:

- Bash (Bourne Again Shell)
- Zsh (Z Shell)
- Fish (Friendly Interactive Shell)

Bash is one of the most commonly used shells in Linux.

## Opening the Terminal

You can open the terminal using:

- `Ctrl + Alt + T` on many Linux desktop distributions.
- The Terminal application from the applications menu.
- SSH when connecting to a remote Linux server.

## Understanding the Terminal Prompt

Example:

```bash
ubuntu@ip-172-31-10-25:~$
```

Explanation:

| Part | Meaning |
|---|---|
| ubuntu | Current username |
| ip-172-31-10-25 | Hostname |
| ~ | Current user's home directory |
| $ | Normal user prompt |

**Note:** The `#` symbol usually indicates a root shell.

## Basic Terminal Commands

### 1. pwd

Displays the current working directory.

```bash
pwd
```

### 2. whoami

Displays the currently logged-in username.

```bash
whoami
```

### 3. hostname

Displays the system hostname.

```bash
hostname
```

### 4. date

Displays the current system date and time.

```bash
date
```

### 5. clear

Clears the terminal screen.

```bash
clear
```

### 6. history

Displays previously executed commands.

```bash
history
```

### 7. man

Displays the manual page for a command.

```bash
man ls
```

Press `q` to exit the manual page.

### 8. echo

Displays text or variable values.

```bash
echo "Hello Linux"
```

## Useful Keyboard Shortcuts

| Shortcut | Purpose |
|---|---|
| Ctrl + C | Stop the running command |
| Ctrl + L | Clear the terminal screen |
| Ctrl + D | Exit the current shell |
| Ctrl + A | Move to the beginning of the line |
| Ctrl + E | Move to the end of the line |
| Tab | Auto-complete commands and paths |
| ↑ / ↓ | Navigate command history |

## Running Commands with sudo

`sudo` allows an authorized user to execute commands with elevated privileges.

Example:

```bash
sudo apt update
```

It may ask for your user's password before executing the command.

## Command Syntax

A general Linux command follows this structure:

```bash
command [options] [arguments]
```

Example:

```bash
ls -l /home/ubuntu
```

- `ls` – Command
- `-l` – Option
- `/home/ubuntu` – Argument

## Real-World Use Cases

- Connecting to AWS EC2 instances.
- Managing Linux servers remotely using SSH.
- Installing and updating software.
- Troubleshooting server issues.
- Running shell scripts and automation tasks.

## Summary

The Linux terminal is an essential tool for system administration. Learning basic commands, shell operations, and keyboard shortcuts makes it easier to manage Linux systems efficiently.