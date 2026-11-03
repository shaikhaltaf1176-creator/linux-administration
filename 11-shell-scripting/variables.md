# Variables in Shell Scripting

## What is a Variable?

A variable is a name used to store a value.

In shell scripting, variables help us store information and reuse it throughout a script.

For example, we can store a username, directory name, or application port.

## 1. Create a Variable

```bash
#!/bin/bash

name="Altaf"

echo $name
```

Output:

```text
Altaf
```

## 2. Variable Naming Rules

- Variable names should not contain spaces.
- Variable names should start with a letter or underscore.
- Variable names are case-sensitive.
- Do not use spaces around the `=` sign.

Correct:

```bash
name="Altaf"
age=25
server_name="Linux"
```

Incorrect:

```bash
name = "Altaf"
```

## 3. Display Variables

Use `$` before the variable name.

```bash
#!/bin/bash

username="admin"
server="EC2"

echo "Username: $username"
echo "Server: $server"
```

## 4. Using Variables in Commands

```bash
#!/bin/bash

directory="backup"

mkdir -p "$directory"

echo "Directory created: $directory"
```

## 5. Read-Only Variables

Use `readonly` to prevent changing a variable's value.

```bash
#!/bin/bash

readonly country="India"

echo "$country"
```

## 6. Environment Variables

Environment variables provide information to processes running in the system.

Common examples:

| Variable | Purpose                    |
| -------- | -------------------------- |
| `$HOME`  | User's home directory      |
| `$USER`  | Current username           |
| `$PATH`  | Command search locations   |
| `$SHELL` | Current user's login shell |
| `$PWD`   | Current working directory  |

Display an environment variable:

```bash
echo $HOME
echo $USER
echo $PATH
```

## 7. Command Substitution

Command substitution stores the output of a command in a variable.

```bash
#!/bin/bash

current_date=$(date)

echo "Today is: $current_date"
```

Another example:

```bash
hostname=$(hostname)

echo "Server name: $hostname"
```

## 8. Special Variables

| Variable   | Meaning                         |
| ---------- | ------------------------------- |
| `$0`       | Script name                     |
| `$1`, `$2` | First and second arguments      |
| `$#`       | Number of arguments             |
| `$@`       | All arguments                   |
| `$?`       | Exit status of the last command |
| `$$`       | Current shell process ID        |

Example:

```bash
#!/bin/bash

echo "Script: $0"
echo "First argument: $1"
echo "Second argument: $2"
echo "Total arguments: $#"
```

Run:

```bash
bash variables.sh Altaf AWS
```

## Practice

1. Create a variable for your name.
2. Store your Linux distribution name.
3. Display your home directory.
4. Store the current date in a variable.
5. Print all values.
