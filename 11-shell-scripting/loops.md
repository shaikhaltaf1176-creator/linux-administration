# Loops in Shell Scripting

## What are Loops?

Loops allow us to execute the same commands multiple times.

Instead of writing the same command repeatedly, we can use a loop to automate the task.

Shell scripting mainly uses three types of loops:

- `for` loop
- `while` loop
- `until` loop

## 1. for Loop

A `for` loop executes commands for each value in a list.

```bash
#!/bin/bash

for name in Altaf Rahul Priya
do
    echo "Hello, $name"
done
```

Output:

```text
Hello, Altaf
Hello, Rahul
Hello, Priya
```

## 2. for Loop with Numbers

```bash
#!/bin/bash

for i in {1..5}
do
    echo "Number: $i"
done
```

Output:

```text
Number: 1
Number: 2
Number: 3
Number: 4
Number: 5
```

## 3. while Loop

A `while` loop continues as long as its condition is true.

```bash
#!/bin/bash

count=1

while [ "$count" -le 5 ]
do
    echo "Count: $count"
    count=$((count + 1))
done
```

## 4. until Loop

An `until` loop continues until its condition becomes true.

```bash
#!/bin/bash

count=1

until [ "$count" -gt 5 ]
do
    echo "Count: $count"
    count=$((count + 1))
done
```

## 5. break Statement

The `break` statement stops a loop immediately.

```bash
#!/bin/bash

for i in {1..10}
do
    if [ "$i" -eq 5 ]; then
        break
    fi

    echo "$i"
done
```

Output:

```text
1
2
3
4
```

## 6. continue Statement

The `continue` statement skips the current iteration and moves to the next one.

```bash
#!/bin/bash

for i in {1..5}
do
    if [ "$i" -eq 3 ]; then
        continue
    fi

    echo "$i"
done
```

Output:

```text
1
2
4
5
```

## 7. Loop Through Files

```bash
#!/bin/bash

for file in *.txt
do
    echo "Found file: $file"
done
```

This displays files ending with `.txt` in the current directory.

## Important Points

- `for` is useful for processing lists and ranges.
- `while` runs while a condition is true.
- `until` runs until a condition becomes true.
- `break` exits a loop.
- `continue` skips the current iteration.

## Practice

1. Print numbers from 1 to 10.
2. Print even numbers from 1 to 20.
3. Create a multiplication table.
4. Display all `.txt` files in a directory.
5. Create a countdown script.
