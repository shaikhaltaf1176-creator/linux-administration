# chown – Change File Ownership

## Introduction

`chown` stands for Change Owner.

It is used to change the ownership of files and directories in Linux.

Every file in Linux has an owner and an associated group. Sometimes administrators need to transfer ownership from one user to another.

The `chown` command makes this possible.

## Basic Syntax

```bash
chown [options] owner filename
```

## Check Current Ownership

Use:

```bash
ls -l
```

Example:

```text
-rw-r--r-- 1 ubuntu ubuntu 1024 Nov 4 10:00 file.txt
```

Here:

- First `ubuntu` – File owner.
- Second `ubuntu` – Associated group.

## 1. Change File Owner

Change ownership to another user:

```bash
sudo chown admin file.txt
```

Now `admin` becomes the file owner.

## 2. Change Owner and Group

Change both owner and group:

```bash
sudo chown admin:developers file.txt
```

Here:

- `admin` – New owner.
- `developers` – New group.

## 3. Change Only Group Using chown

```bash
sudo chown :developers file.txt
```

This changes the file's group without changing its owner.

## 4. Change Ownership Recursively

Use `-R` to change ownership of a directory and everything inside it.

```bash
sudo chown -R admin:developers /home/project
```

## 5. Change Ownership of Multiple Files

```bash
sudo chown admin file1.txt file2.txt file3.txt
```

## Practical Example

Create a file:

```bash
sudo touch project.txt
```

Check ownership:

```bash
ls -l project.txt
```

Change the owner:

```bash
sudo chown ubuntu project.txt
```

Verify the change:

```bash
ls -l project.txt
```

## Difference Between chown and chmod

| chown                            | chmod                               |
| -------------------------------- | ----------------------------------- |
| Changes file ownership           | Changes file permissions            |
| Changes owner or group           | Changes read, write, execute access |
| Example: `chown ubuntu file.txt` | Example: `chmod 644 file.txt`       |

## Real-World Use Cases

- Assigning application files to the correct user.
- Managing website ownership.
- Fixing file ownership issues.
- Managing project directories on EC2 instances.
- Giving application users access to required files.

## Summary

The `chown` command is used to change file and directory ownership. It helps administrators manage which users and groups own system resources.
