# chgrp – Change Group Ownership

## Introduction

`chgrp` stands for Change Group.

It is used to change the group ownership of files and directories in Linux.

Linux groups make it easier to manage permissions for multiple users. Instead of assigning access individually, administrators can assign files to a group and manage access through group permissions.

## Basic Syntax

```bash
chgrp [options] groupname filename
```

## Check Current Group Ownership

```bash
ls -l file.txt
```

Example output:

```text
-rw-r--r-- 1 ubuntu developers 1024 Nov 4 10:00 file.txt
```

Here, `developers` is the group associated with the file.

## 1. Change Group Ownership

Change the group of a file:

```bash
sudo chgrp developers file.txt
```

Now the file belongs to the `developers` group.

## 2. Change Group of Multiple Files

```bash
sudo chgrp developers file1.txt file2.txt
```

## 3. Change Group Recursively

Use `-R` to change the group of a directory and all its contents.

```bash
sudo chgrp -R developers /home/project
```

## 4. Verify Group Ownership

```bash
ls -l file.txt
```

You can also use:

```bash
stat file.txt
```

## Practical Example

Create a group:

```bash
sudo groupadd developers
```

Create a file:

```bash
touch project.txt
```

Change its group:

```bash
sudo chgrp developers project.txt
```

Verify:

```bash
ls -l project.txt
```

## Difference Between chown and chgrp

| Command | Purpose |
|---|---|
| `chown` | Changes owner and optionally group |
| `chgrp` | Changes group ownership only |

Example:

```bash
sudo chown ubuntu:developers file.txt
sudo chgrp developers file.txt
```

Both can change the group, but `chown` can also change the owner.

## Real-World Use Cases

- Sharing files between team members.
- Managing project directories.
- Assigning application files to specific groups.
- Controlling access on multi-user Linux servers.

## Summary

The `chgrp` command changes the group ownership of files and directories. It is useful when multiple users need shared access to common resources.