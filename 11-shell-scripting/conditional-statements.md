# Conditional Statements in Shell Scripting

## What are Conditional Statements?

Conditional statements allow a script to make decisions.

They execute different commands depending on whether a condition is true or false.

For example:

- Check whether a file exists.
- Check whether a user is root.
- Check whether a service is running.
- Compare two numbers.

## 1. if Statement

The `if` statement executes code when a condition is true.

```bash
#!/bin/bash

age=20

if [ "$age" -ge 18 ]; then
    echo "You are an adult"
fi
```

## 2. if-else Statement

The `else` block runs when the condition is false.

```bash
#!/bin/bash

age=16

if [ "$age" -ge 18 ]; then
    echo "You are eligible"
else
    echo "You are not eligible"
fi
```

## 3. if-elif-else Statement

Use `elif` when you need to check multiple conditions.

```bash
#!/bin/bash

marks=75

if [ "$marks" -ge 90 ]; then
    echo "Grade A"
elif [ "$marks" -ge 70 ]; then
    echo "Grade B"
elif [ "$marks" -ge 50 ]; then
    echo "Grade C"
else
    echo "Fail"
fi
```

## 4. Comparison Operators

### Numeric Comparisons

| Operator | Meaning               |
| -------- | --------------------- |
| `-eq`    | Equal                 |
| `-ne`    | Not equal             |
| `-gt`    | Greater than          |
| `-lt`    | Less than             |
| `-ge`    | Greater than or equal |
| `-le`    | Less than or equal    |

Example:

```bash
#!/bin/bash

num=10

if [ "$num" -gt 5 ]; then
    echo "Number is greater than 5"
fi
```

### String Comparisons

| Operator | Meaning             |
| -------- | ------------------- |
| `=`      | Equal               |
| `!=`     | Not equal           |
| `-z`     | String is empty     |
| `-n`     | String is not empty |

Example:

```bash
#!/bin/bash

name="Altaf"

if [ "$name" = "Altaf" ]; then
    echo "Name matched"
fi
```

## 5. File Conditions

Linux shell scripts can check whether files and directories exist.

| Operator | Meaning                   |
| -------- | ------------------------- |
| `-f`     | Regular file exists       |
| `-d`     | Directory exists          |
| `-e`     | File or directory exists  |
| `-r`     | Read permission exists    |
| `-w`     | Write permission exists   |
| `-x`     | Execute permission exists |

Example:

```bash
#!/bin/bash

file="test.txt"

if [ -f "$file" ]; then
    echo "File exists"
else
    echo "File does not exist"
fi
```

## 6. Logical Operators

Use logical operators to combine conditions.

### AND (`&&`)

Both conditions must be true.

```bash
if [ "$age" -ge 18 ] && [ "$age" -le 60 ]; then
    echo "Age is between 18 and 60"
fi
```

### OR (`||`)

At least one condition must be true.

```bash
if [ "$name" = "Altaf" ] || [ "$name" = "Admin" ]; then
    echo "Access allowed"
fi
```

## 7. case Statement

The `case` statement is useful when checking multiple possible values.

```bash
#!/bin/bash

read -p "Enter an option (start/stop/restart): " action

case "$action" in
    start)
        echo "Starting service"
        ;;
    stop)
        echo "Stopping service"
        ;;
    restart)
        echo "Restarting service"
        ;;
    *)
        echo "Invalid option"
        ;;
esac
```

## Important Points

- `if` checks a condition.
- `else` handles the false condition.
- `elif` checks additional conditions.
- `case` matches a value against multiple patterns.
- Always close an `if` block with `fi`.

## Practice

1. Check whether a number is positive or negative.
2. Check whether a number is even or odd.
3. Check whether a file exists.
4. Create a script to check whether Nginx is running.
5. Create a menu using `case`.
