# Practical Shell Scripts in Linux

## Introduction

Shell scripting becomes more useful when we apply it to real Linux administration tasks.

In this section, we will create practical scripts commonly used by Linux and AWS administrators.

## 1. System Information Script

This script displays basic information about the Linux server.

```bash
#!/bin/bash

echo "===== SYSTEM INFORMATION ====="

echo "Hostname:"
hostname

echo "Current User:"
whoami

echo "Date:"
date

echo "Kernel Version:"
uname -r

echo "Uptime:"
uptime
```

Save as:

```bash
system-info.sh
```

Run:

```bash
chmod +x system-info.sh
./system-info.sh
```

## 2. Disk Usage Monitoring Script

This script displays disk usage.

```bash
#!/bin/bash

echo "===== DISK USAGE ====="

df -h

echo "===== STORAGE CHECK COMPLETED ====="
```

Save as:

```bash
disk-check.sh
```

Run:

```bash
chmod +x disk-check.sh
./disk-check.sh
```

## 3. Backup Script

This script creates a compressed backup of a directory.

```bash
#!/bin/bash

SOURCE="/home/ubuntu/Documents"
BACKUP="/home/ubuntu/backup"

mkdir -p "$BACKUP"

DATE=$(date +%Y-%m-%d_%H-%M-%S)

tar -czf "$BACKUP/backup-$DATE.tar.gz" -C "$(dirname "$SOURCE")" "$(basename "$SOURCE")"

echo "Backup completed successfully"
```

Save as:

```bash
backup.sh
```

Update the source and backup paths according to your system before running it.

## 4. User Information Script

```bash
#!/bin/bash

read -p "Enter username: " username

echo "Username: $username"

if id "$username" &>/dev/null; then
    echo "User exists"
else
    echo "User does not exist"
fi
```

Save as:

```bash
user-check.sh
```

## 5. Service Monitoring Script

This script checks whether Nginx is running.

```bash
#!/bin/bash

SERVICE="nginx"

if systemctl is-active --quiet "$SERVICE"; then
    echo "$SERVICE is running"
else
    echo "$SERVICE is not running"
fi
```

Save as:

```bash
service-check.sh
```

Run:

```bash
chmod +x service-check.sh
./service-check.sh
```

## 6. Simple Calculator

```bash
#!/bin/bash

read -p "Enter first number: " num1
read -p "Enter second number: " num2

echo "Addition: $((num1 + num2))"
echo "Subtraction: $((num1 - num2))"
echo "Multiplication: $((num1 * num2))"

if [ "$num2" -ne 0 ]; then
    echo "Division: $((num1 / num2))"
else
    echo "Division is not possible by zero"
fi
```

Save as:

```bash
calculator.sh
```

## 7. Directory Creation Script

```bash
#!/bin/bash

read -p "Enter directory name: " dirname

if [ -d "$dirname" ]; then
    echo "Directory already exists"
else
    mkdir -p "$dirname"
    echo "Directory created successfully"
fi
```

Save as:

```bash
create-directory.sh
```

## 8. Log Monitoring Script

This script displays the latest system log entries.

For Ubuntu:

```bash
#!/bin/bash

echo "Latest system logs:"

sudo tail -n 20 /var/log/syslog
```

For Amazon Linux 2023:

```bash
#!/bin/bash

echo "Latest system logs:"

sudo journalctl -n 20
```

Save as:

```bash
log-check.sh
```

## 9. Run Multiple Scripts

You can create one main script that runs other scripts.

```bash
#!/bin/bash

echo "Starting system checks"

./system-info.sh
./disk-check.sh
./service-check.sh

echo "All checks completed"
```

Save as:

```bash
main.sh
```

Make the scripts executable before running the main script.

## Important Points

- Shell scripts automate repetitive administration tasks.
- Always test scripts before using them on production servers.
- Use variables to avoid repeating values.
- Use conditions to handle errors.
- Use meaningful filenames and comments.
- Be careful when scripts modify or delete files.

## Practice Projects

1. Create a script to monitor disk usage.
2. Create a script to check whether Nginx is running.
3. Create an automatic backup script.
4. Create a script to display system information.
5. Create a menu-driven Linux administration script.
6. Create a script that checks disk usage and prints a warning when usage exceeds a chosen threshold.

These practical scripts are useful for Linux administration and AWS EC2 server management.
