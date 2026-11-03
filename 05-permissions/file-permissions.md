# Linux File Permissions

## Introduction

Linux is a multi-user operating system, which means multiple users can access the same system. To keep files and directories secure, Linux uses a permission system.

File permissions control who can read, modify, or execute a file.

Linux permissions are divided into three categories:

1. Owner – The user who owns the file.
2. Group – Users who belong to the file's assigned group.
3. Others – Everyone else on the system.

## Types of Permissions

Linux provides three basic permissions:

| Permission | Symbol | Value | Description |
|---|---|---|---|
| Read | r | 4 | View file contents |
| Write | w | 2 | Modify file contents |
| Execute | x | 1 | Execute a file |

For directories:
- Read (`r`) – List directory contents.
- Write (`w`) – Create, delete, or rename entries, subject to other restrictions.
- Execute (`x`) – Access entries inside the directory.

## Understanding Permission Output

Run:

```bash
ls -l
```

Example output:

```text
-rwxr-xr-- 1 ubuntu developers 1200 Nov 4 10:00 script.sh
```

Explanation:

```text
- rwx r-x r--
  |   |   |
  |   |   └── Others
  |   └────── Group
  └────────── Owner
```

- `-` – Regular file.
- `rwx` – Owner has read, write, and execute permissions.
- `r-x` – Group has read and execute permissions.
- `r--` – Others have read-only permission.

## Checking File Permissions

```bash
ls -l filename
```

Check directory permissions:

```bash
ls -ld /home/ubuntu
```

## Permission Values

| Permission | Calculation | Value |
|---|---|---|
| Read + Write + Execute | 4+2+1 | 7 |
| Read + Write | 4+2 | 6 |
| Read + Execute | 4+1 | 5 |
| Read only | 4 | 4 |
| No permission | 0 | 0 |

## Common Permission Examples

| Permission | Meaning |
|---|---|
| 777 | Everyone has full permissions |
| 755 | Owner has full access; others can read and execute |
| 700 | Only owner has full access |
| 644 | Owner can read/write; others can only read |
| 600 | Only owner can read/write |

## Practical Commands

Create a file:

```bash
touch file.txt
```

Check permissions:

```bash
ls -l file.txt
```

Change permissions:

```bash
chmod 644 file.txt
```

## Real-World Use Cases

- Protecting important configuration files.
- Preventing unauthorized file modifications.
- Controlling access to application files.
- Securing Linux servers.

## Summary

Linux file permissions help control access to files and directories. Understanding read, write, and execute permissions is essential for Linux system administration.