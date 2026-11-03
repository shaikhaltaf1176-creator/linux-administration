# Lab 08: Shell Scripting in Linux

## Objective

Create and execute shell scripts to automate common Linux administration tasks.

## Requirements

- Ubuntu or Amazon Linux.
- Terminal access.
- Bash shell.

## Step 1: Check Bash Version

```bash
bash --version
```

## Step 2: Create a Script

```bash
nano system-info.sh
```

Add:

```bash
#!/bin/bash

echo "===== SYSTEM INFORMATION ====="

echo "Hostname:"
hostname

echo "Current User:"
whoami

echo "Current Date:"
date

echo "Disk Usage:"
df -h

echo "Memory Usage:"
free -h
```

## Step 3: Give Execute Permission

```bash
chmod +x system-info.sh
```

## Step 4: Execute the Script

```bash
./system-info.sh
```

## Step 5: Create a User Input Script

Create:

```bash
nano user-info.sh
```

Add:

```bash
#!/bin/bash

read -p "Enter your name: " name
read -p "Enter your course: " course

echo "Name: $name"
echo "Course: $course"
```

Run:

```bash
chmod +x user-info.sh
./user-info.sh
```

## Step 6: Create a Conditional Script

Create:

```bash
nano file-check.sh
```

Add:

```bash
#!/bin/bash

read -p "Enter file name: " filename

if [ -f "$filename" ]; then
    echo "File exists"
else
    echo "File does not exist"
fi
```

Run:

```bash
chmod +x file-check.sh
./file-check.sh
```

## Step 7: Create a Loop Script

Create:

```bash
nano numbers.sh
```

Add:

```bash
#!/bin/bash

for i in {1..10}
do
    echo "Number: $i"
done
```

Run:

```bash
chmod +x numbers.sh
./numbers.sh
```

## Step 8: Create a Disk Monitoring Script

Create:

```bash
nano disk-monitor.sh
```

Add:

```bash
#!/bin/bash

THRESHOLD=80

USAGE=$(df -P / | awk 'NR==2 {gsub("%","",$5); print $5}')

echo "Current root disk usage: ${USAGE}%"

if [ "$USAGE" -ge "$THRESHOLD" ]; then
    echo "WARNING: Disk usage is above the threshold!"
else
    echo "Disk usage is normal."
fi
```

Run:

```bash
chmod +x disk-monitor.sh
./disk-monitor.sh
```

## Step 9: Create a Backup Script

Create:

```bash
nano backup.sh
```

Add:

```bash
#!/bin/bash

SOURCE="$HOME/Documents"
BACKUP="$HOME/backups"

mkdir -p "$BACKUP"

DATE=$(date +%Y-%m-%d_%H-%M-%S)

if [ -d "$SOURCE" ]; then
    tar -czf "$BACKUP/backup-$DATE.tar.gz" -C "$HOME" Documents
    echo "Backup completed successfully"
else
    echo "Source directory does not exist"
fi
```

This script backs up the user's Documents directory into a compressed archive.

Run:

```bash
chmod +x backup.sh
./backup.sh
```

## Step 10: Verify Backup

```bash
ls -lh ~/backups
```

## Final Practice Tasks

1. Create a script to display system information.
2. Create a script to check whether a file exists.
3. Create a script to monitor disk usage.
4. Create a script to back up a directory.
5. Create a menu-driven script for basic Linux administration.

## Expected Result

You successfully created and executed shell scripts for system information, user input, conditions, loops, disk monitoring, and backups.

## What I Learned

- Creating shell scripts.
- Using variables.
- Accepting user input.
- Writing conditional statements.
- Using loops.
- Automating Linux administration tasks.

## Final Outcome

Shell scripting helps Linux and AWS administrators automate repetitive tasks and manage servers more efficiently.
