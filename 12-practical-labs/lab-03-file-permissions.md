# Lab 03: File Permissions in Linux

## Objective

Understand and manage Linux file and directory permissions using `chmod`, `chown`, and `chgrp`.

## Requirements

- Ubuntu or Amazon Linux.
- Terminal access.
- Sudo privileges.

## Step 1: Create a Directory

```bash
mkdir linux-permissions
cd linux-permissions
```

## Step 2: Create a File

```bash
touch sample.txt
```

Add some content:

```bash
echo "Learning Linux permissions" > sample.txt
```

## Step 3: Check File Permissions

```bash
ls -l sample.txt
```

Example output:

```text
-rw-r--r-- 1 user user 28 Nov 4 10:00 sample.txt
```

The permission section represents:

- Owner permissions: `rw-`
- Group permissions: `r--`
- Others permissions: `r--`

## Step 4: Change Permissions Using chmod

Give the owner read, write, and execute permissions:

```bash
chmod 700 sample.txt
```

Check the result:

```bash
ls -l sample.txt
```

## Step 5: Understand Numeric Permissions

| Number | Permission             |
| ------ | ---------------------- |
| 0      | No permission          |
| 1      | Execute                |
| 2      | Write                  |
| 3      | Write + Execute        |
| 4      | Read                   |
| 5      | Read + Execute         |
| 6      | Read + Write           |
| 7      | Read + Write + Execute |

Example:

```bash
chmod 755 sample.txt
```

## Step 6: Change File Ownership

Create a test user if required:

```bash
sudo adduser developer
```

Change file ownership:

```bash
sudo chown developer sample.txt
```

Verify:

```bash
ls -l sample.txt
```

## Step 7: Change Group Ownership

```bash
sudo groupadd developers
sudo chgrp developers sample.txt
```

Verify:

```bash
ls -l sample.txt
```

## Step 8: Change Permissions Recursively

Create a directory and files:

```bash
mkdir project
touch project/file1.txt project/file2.txt
```

Change permissions for the directory and its contents:

```bash
chmod -R 755 project
```

**Note:** Recursive permission changes should be used carefully, especially on system directories.

## Verification

```bash
ls -l
ls -ld project
```

Confirm that the owner, group, and permissions have changed.

## Expected Result

You successfully changed file permissions, ownership, and group ownership.

## What I Learned

- Understanding Linux permissions.
- Using `chmod`.
- Using `chown`.
- Using `chgrp`.
- Managing directory permissions.
