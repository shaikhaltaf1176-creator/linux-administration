# chmod – Change File Permissions

## Introduction

`chmod` stands for Change Mode.

It is used to change the permissions of files and directories in Linux.

Using chmod, administrators can control which users are allowed to read, write, or execute files.

## Basic Syntax

```bash
chmod [permissions] filename
```

There are two common ways to use chmod:

1. Numeric method.
2. Symbolic method.

## 1. Numeric Method

Linux assigns a numeric value to each permission.

| Permission  | Value |
| ----------- | ----- |
| Read (r)    | 4     |
| Write (w)   | 2     |
| Execute (x) | 1     |

Add the values to create a permission number.

Example:

```text
rwx = 4 + 2 + 1 = 7
rw- = 4 + 2 = 6
r-x = 4 + 1 = 5
r-- = 4
```

### Common chmod Examples

Give the owner full permissions, group and others read-only access:

```bash
chmod 744 file.txt
```

Give everyone read and write permissions:

```bash
chmod 666 file.txt
```

Give the owner full permissions and group and others read/execute permissions:

```bash
chmod 755 script.sh
```

Give the owner read/write permissions and group and others read-only permissions:

```bash
chmod 644 file.txt
```

Remove all permissions from everyone:

```bash
chmod 000 file.txt
```

## 2. Symbolic Method

The symbolic method uses letters to change permissions.

| Symbol | Meaning              |
| ------ | -------------------- |
| u      | Owner (user)         |
| g      | Group                |
| o      | Others               |
| a      | All users            |
| +      | Add permission       |
| -      | Remove permission    |
| =      | Set exact permission |

### Examples

Add execute permission to the owner:

```bash
chmod u+x script.sh
```

Remove write permission from others:

```bash
chmod o-w file.txt
```

Add read permission to everyone:

```bash
chmod a+r file.txt
```

Give the group read and write permissions:

```bash
chmod g+rw file.txt
```

Set exact permissions for the owner:

```bash
chmod u=rwx file.txt
```

## Recursive Permissions

The `-R` option applies permissions to a directory and its contents.

Example:

```bash
chmod -R 755 myfolder
```

Use recursive permission changes carefully, especially on system directories.

## Practical Example

Create a script:

```bash
touch backup.sh
```

Add script content:

```bash
echo 'echo "Backup started"' > backup.sh
```

Make it executable:

```bash
chmod +x backup.sh
```

Run the script:

```bash
./backup.sh
```

## Verify Permissions

```bash
ls -l backup.sh
```

## Real-World Use Cases

- Making shell scripts executable.
- Protecting configuration files.
- Controlling access to application directories.
- Managing permissions on AWS EC2 instances.

## Summary

The `chmod` command changes file and directory permissions. The numeric and symbolic methods provide flexible ways to manage access in Linux.
