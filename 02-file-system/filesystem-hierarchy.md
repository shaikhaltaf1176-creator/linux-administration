# Linux Filesystem Hierarchy (FHS)

## Introduction

The Filesystem Hierarchy Standard (FHS) defines a common directory structure for Linux and other Unix-like operating systems.

It helps maintain consistency across Linux distributions by defining where different types of files and directories should be located.

For example, system configuration files are generally stored in `/etc`, while system logs are stored in `/var/log`.

## What is FHS?

FHS stands for Filesystem Hierarchy Standard.

Its main purpose is to provide a standard way to organize files and directories.

It helps:

- Linux administrators find files easily.
- Developers organize application files.
- Software packages use consistent locations.
- Different Linux distributions follow a common structure.

## Main Filesystem Categories

### 1. Static Files

These files generally do not change during normal system operation.

Examples:

- `/bin`
- `/sbin`
- `/usr`
- `/etc`

### 2. Variable Files

These files change frequently while the system is running.

Examples:

- `/var/log`
- `/var/cache`
- `/var/spool`

### 3. Temporary Files

These files are created temporarily and may be removed automatically.

Examples:

- `/tmp`
- `/var/tmp`

### 4. User Files

These directories contain user-related data.

Examples:

- `/home`
- `/root`

### 5. Virtual Filesystems

These filesystems provide information about the kernel, processes, and hardware.

Examples:

- `/proc`
- `/sys`
- `/dev`

## Linux Filesystem Hierarchy

```text
/
├── bin
├── boot
├── dev
├── etc
├── home
├── lib
├── media
├── mnt
├── opt
├── proc
├── root
├── run
├── sbin
├── srv
├── sys
├── tmp
├── usr
└── var
```

## Important FHS Directories

| Directory | Purpose                           |
| --------- | --------------------------------- |
| `/bin`    | Essential user commands           |
| `/boot`   | Boot-related files                |
| `/dev`    | Device files                      |
| `/etc`    | Configuration files               |
| `/home`   | User directories                  |
| `/lib`    | Essential shared libraries        |
| `/media`  | Removable media                   |
| `/mnt`    | Temporary mount points            |
| `/opt`    | Optional software                 |
| `/proc`   | Process and kernel information    |
| `/root`   | Root user's home directory        |
| `/run`    | Runtime data                      |
| `/sbin`   | System administration commands    |
| `/srv`    | Data served by system services    |
| `/sys`    | Kernel and device information     |
| `/tmp`    | Temporary files                   |
| `/usr`    | Applications and shared resources |
| `/var`    | Variable data and logs            |

## FHS vs Linux Directory Structure

These terms are related but not identical.

- Linux directory structure describes how directories are organized in a Linux system.
- FHS defines the standard and conventions used to organize those directories.

## Practical Commands

View the root directory:

```bash
ls /
```

Check mounted filesystems:

```bash
df -h
```

Display filesystem types:

```bash
df -Th
```

Check disk usage:

```bash
du -sh /var/log
```

## Real-World Use Cases

- Maintaining consistent Linux server configurations.
- Locating application and system files.
- Managing logs and storage.
- Troubleshooting Linux systems.
- Working with different Linux distributions.

## Summary

The Filesystem Hierarchy Standard provides a common structure for organizing Linux files and directories. Learning FHS makes it easier to manage and troubleshoot different Linux distributions.
