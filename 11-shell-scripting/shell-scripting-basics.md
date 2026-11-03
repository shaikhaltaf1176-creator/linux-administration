# Shell Scripting Basics in Linux

## What is Shell Scripting?

Shell scripting is a way to automate tasks in Linux by writing multiple commands inside a file.

Instead of running commands one by one, we can write them in a script and execute everything together.

For example, we can create a script to:

- Update Linux packages.
- Create directories.
- Back up files.
- Monitor disk usage.
- Start or stop services.

## 1. What is a Shell?

A shell is a program that accepts commands from users and passes them to the operating system for execution.

Common Linux shells include:

- Bash
- Zsh
- Sh
- Fish

Bash (Bourne Again Shell) is one of the most commonly used shells.

## 2. Check Your Current Shell

```bash
echo $SHELL
```

Check the Bash version:

```bash
bash --version
```

## 3. Create Your First Shell Script

Create a file:

```bash
nano hello.sh
```

Add this code:

```bash
#!/bin/bash

echo "Hello, Linux!"
echo "Welcome to Shell Scripting"
```

Save the file.

## 4. Give Execute Permission

```bash
chmod +x hello.sh
```

## 5. Run the Script

```bash
./hello.sh
```

Output:

```text
Hello, Linux!
Welcome to Shell Scripting
```

You can also run it using Bash:

```bash
bash hello.sh
```

## 6. Understand the Shebang

```bash
#!/bin/bash
```

The first line is called the shebang.

It tells the operating system which interpreter should execute the script.

## 7. Comments in Shell Scripts

Comments are used to explain code. They are not executed.

```bash
#!/bin/bash

# This is a comment

echo "Learning Linux"
```

## 8. Multiple Commands in One Script

```bash
#!/bin/bash

echo "Checking system information"

date
hostname
whoami
pwd
```

## Important Points

- Shell scripts automate Linux tasks.
- Bash is a commonly used shell.
- Shell scripts usually use the `.sh` extension.
- `chmod +x` gives execute permission.
- `./script.sh` executes a script from the current directory.

## Practice

1. Create a file named `hello.sh`.
2. Print your name.
3. Display the current date.
4. Display the hostname.
5. Run the script.