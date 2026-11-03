# Functions in Shell Scripting

## What is a Function?

A function is a reusable block of code that performs a specific task.

Instead of writing the same commands multiple times, we can create a function and call it whenever needed.

Functions help make shell scripts cleaner and easier to maintain.

## 1. Create a Function

```bash
#!/bin/bash

greet() {
    echo "Hello, Welcome to Linux!"
}

greet
```

Output:

```text
Hello, Welcome to Linux!
```

## 2. Function with Parameters

We can pass values to a function.

```bash
#!/bin/bash

greet() {
    echo "Hello, $1"
}

greet "Altaf"
```

Output:

```text
Hello, Altaf
```

Here, `$1` represents the first argument passed to the function.

## 3. Function with Multiple Parameters

```bash
#!/bin/bash

user_info() {
    echo "Name: $1"
    echo "Course: $2"
}

user_info "Altaf" "AWS"
```

Output:

```text
Name: Altaf
Course: AWS
```

## 4. Function with a Return Status

A shell function can return an exit status using `return`.

```bash
#!/bin/bash

check_file() {
    if [ -f "$1" ]; then
        echo "File exists"
        return 0
    else
        echo "File not found"
        return 1
    fi
}

check_file "test.txt"

echo "Exit status: $?"
```

The exit status is normally:

- `0` – Success.
- Non-zero – Failure or another condition.

## 5. Store Function Output in a Variable

Use command substitution to capture output printed by a function.

```bash
#!/bin/bash

get_date() {
    date
}

today=$(get_date)

echo "Current date: $today"
```

## 6. Create Multiple Functions

```bash
#!/bin/bash

start_service() {
    echo "Starting service"
}

stop_service() {
    echo "Stopping service"
}

restart_service() {
    echo "Restarting service"
}

start_service
stop_service
restart_service
```

## 7. Real-World Example: Disk Usage Function

```bash
#!/bin/bash

check_disk() {
    echo "Checking disk usage..."
    df -h
}

check_disk
```

## Important Points

- Functions help reuse code.
- Functions are defined before they are called in simple scripts.
- `$1`, `$2`, and other positional parameters represent function arguments inside the function.
- `return` sets an exit status, not a general text result.
- Command substitution captures a function's printed output.

## Practice

1. Create a function to display your name.
2. Create a function to display the current date.
3. Create a function to check disk usage.
4. Create a function that accepts two numbers.
5. Create a function to check whether a file exists.
