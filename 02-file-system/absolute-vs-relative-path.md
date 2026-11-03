# Absolute Path vs Relative Path in Linux

## Introduction

A path tells Linux where a particular file or directory is located.

Linux supports two main types of paths:

1. Absolute Path
2. Relative Path

Understanding the difference makes navigating the Linux filesystem much easier.

## 1. Absolute Path

An absolute path specifies the complete location of a file or directory starting from the root directory `/`.

It always begins with `/`.

Example:

```bash
/home/ubuntu/documents/file.txt
```

This path identifies the same location regardless of your current working directory.

### Example

```bash
cd /home/ubuntu
pwd
```

Output:

```text
/home/ubuntu
```

Create a directory using an absolute path:

```bash
mkdir /home/ubuntu/projects
```

## 2. Relative Path

A relative path specifies the location of a file or directory based on your current working directory.

It does not start with `/`.

Example:

```bash
documents/file.txt
```

### Example

Suppose your current directory is:

```text
/home/ubuntu
```

You can navigate to the documents directory using:

```bash
cd documents
```

You can also navigate to the parent directory using:

```bash
cd ..
```

## Special Path Symbols

| Symbol | Meaning                       |
| ------ | ----------------------------- |
| `/`    | Root directory                |
| `.`    | Current directory             |
| `..`   | Parent directory              |
| `~`    | Current user's home directory |
| `-`    | Previous working directory    |

## Practical Examples

Check the current directory:

```bash
pwd
```

Navigate using an absolute path:

```bash
cd /var/log
```

Navigate using a relative path:

```bash
cd Documents
```

Move to the parent directory:

```bash
cd ..
```

Move to the home directory:

```bash
cd ~
```

Return to the previous directory:

```bash
cd -
```

## Difference Between Absolute and Relative Paths

| Absolute Path                    | Relative Path                       |
| -------------------------------- | ----------------------------------- |
| Starts with `/`                  | Does not start with `/`             |
| Complete location                | Location based on current directory |
| Independent of current directory | Depends on current directory        |
| Example: `/home/ubuntu`          | Example: `Documents`                |

## Real-World Use Cases

- Navigating Linux directories.
- Writing shell scripts.
- Accessing application configuration files.
- Managing files on remote EC2 instances.

## Summary

An absolute path gives the complete location from the root directory, while a relative path identifies a location based on the current working directory.
