# User Input in Shell Scripting

## What is User Input?

User input allows a shell script to accept information from someone running it.

Instead of writing every value inside the script, we can ask the user to enter values while the script is running.

The `read` command is commonly used for this purpose.

## 1. Read User Input

```bash
#!/bin/bash

echo "Enter your name:"
read name

echo "Welcome, $name"
```

Output:

```text
Enter your name:
Altaf
Welcome, Altaf
```

## 2. Use read with a Prompt

We can use `-p` to display a message and accept input on the same line.

```bash
#!/bin/bash

read -p "Enter your name: " name

echo "Hello, $name"
```

## 3. Accept Multiple Inputs

```bash
#!/bin/bash

read -p "Enter your first name: " first_name
read -p "Enter your last name: " last_name

echo "Full Name: $first_name $last_name"
```

## 4. Accept Hidden Input

Use `-s` to hide input while typing.

This is useful for passwords.

```bash
#!/bin/bash

read -sp "Enter password: " password

echo
echo "Password received"
```

The password is not displayed while typing.

Avoid printing or logging passwords.

## 5. Read Numbers

```bash
#!/bin/bash

read -p "Enter first number: " num1
read -p "Enter second number: " num2

sum=$((num1 + num2))

echo "Sum: $sum"
```

## 6. Read Input with a Default Value

```bash
#!/bin/bash

read -p "Enter your username [admin]: " username

username=${username:-admin}

echo "Username: $username"
```

If the user presses Enter without typing anything, the default value `admin` is used.

## 7. Accept Input as Script Arguments

We can also pass values while running a script.

Create `input.sh`:

```bash
#!/bin/bash

echo "Name: $1"
echo "Course: $2"
```

Run:

```bash
bash input.sh Altaf AWS
```

Output:

```text
Name: Altaf
Course: AWS
```

## Practice

1. Ask the user for their name.
2. Ask for their age.
3. Ask for their city.
4. Display all entered information.
5. Create a calculator that accepts two numbers from the user.
