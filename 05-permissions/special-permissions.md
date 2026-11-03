# Special Permissions in Linux

## Introduction

Linux provides three special permissions in addition to the normal read, write, and execute permissions.

These permissions provide additional control over how files and directories behave.

The three special permissions are:

1. SUID (Set User ID)
2. SGID (Set Group ID)
3. Sticky Bit

## 1. SUID – Set User ID

SUID is mainly used with executable files.

When a file has SUID enabled, it runs with the permissions of the file owner rather than the user who executes it.

### Example

The `passwd` command allows users to change their passwords.

```bash
ls -l /usr/bin/passwd
```

You may see:

```text
-rwsr-xr-x
```

The `s` in the owner's execute position indicates SUID.

### Set SUID

```bash
sudo chmod u+s filename
```

Remove SUID:

```bash
sudo chmod u-s filename
```

Numeric value: `4`

## 2. SGID – Set Group ID

SGID has two common uses.

**For executable files:**

The program runs with the file's group privileges.

**For directories:**

New files and subdirectories inherit the directory's group ownership.

This is useful when multiple users work on the same project.

### Set SGID

```bash
sudo chmod g+s project
```

Remove SGID:

```bash
sudo chmod g-s project
```

Numeric value: `2`

### Example

```bash
sudo groupadd developers
sudo mkdir /shared-project
sudo chgrp developers /shared-project
sudo chmod 2775 /shared-project
```

New files created inside this directory normally inherit the `developers` group.

## 3. Sticky Bit

The sticky bit is commonly used on shared directories.

It prevents ordinary users from deleting or renaming files belonging to other users, even when the directory allows writing.

### Example

The `/tmp` directory commonly has sticky bit enabled.

Check it:

```bash
ls -ld /tmp
```

Example output:

```text
drwxrwxrwt
```

The `t` at the end indicates the sticky bit.

### Set Sticky Bit

```bash
sudo chmod +t shared-folder
```

Remove Sticky Bit:

```bash
sudo chmod -t shared-folder
```

Numeric value: `1`

## Numeric Values of Special Permissions

| Permission | Symbol | Numeric Value |
| ---------- | ------ | ------------- |
| SUID       | s      | 4             |
| SGID       | s      | 2             |
| Sticky Bit | t      | 1             |

## Combined Special Permissions

Special permission values can be combined with normal permissions.

Example:

```bash
chmod 4755 file.sh
```

- `4` – SUID.
- `755` – Normal permissions.

Another example:

```bash
chmod 2775 shared-folder
```

- `2` – SGID.
- `775` – Normal permissions.

## Quick Comparison

| Permission | Purpose                                                                                 |
| ---------- | --------------------------------------------------------------------------------------- |
| SUID       | Executable runs with file owner's privileges                                            |
| SGID       | Executable uses file group privileges; directories pass group ownership to new contents |
| Sticky Bit | Restricts deletion and renaming of other users' files in shared directories             |

## Real-World Use Cases

- SUID: Allowing controlled privileged operations.
- SGID: Managing shared project directories.
- Sticky Bit: Protecting files in shared directories such as `/tmp`.

## Security Note

Special permissions should be used carefully. Unnecessary SUID or SGID permissions can create security risks.

Avoid applying special permissions to unknown executables.

## Summary

SUID, SGID, and Sticky Bit provide additional access control in Linux. They are especially useful for managing shared directories and controlled privileged operations.
