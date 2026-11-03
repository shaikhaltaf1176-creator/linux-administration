# Important Directories in Linux

## Introduction

Linux contains several important directories, and each directory has a specific purpose. As a Linux administrator, you should understand where configuration files, logs, applications, and user data are stored.

## Important Linux Directories

### 1. / (Root)

The main directory of the entire Linux filesystem.

```bash
cd /
ls
```

### 2. /home

Stores home directories for regular users.

Example:

```text
/home/
├── ubuntu/
├── ec2-user/
└── admin/
```

Each user normally has a separate home directory.

### 3. /root

The home directory of the root administrator.

```bash
cd /root
```

Unlike `/home`, this directory belongs specifically to the root user.

### 4. /etc

Contains system-wide configuration files.

Examples:

```text
/etc/hostname
/etc/hosts
/etc/fstab
/etc/ssh/sshd_config
```

### 5. /var

Stores files that frequently change during system operation.

Important subdirectories:

- `/var/log` – System and application logs.
- `/var/cache` – Cached application data.
- `/var/lib` – Application state data.
- `/var/www` – Common location for website files.

### 6. /tmp

Stores temporary files.

```bash
cd /tmp
```

Temporary files may be removed automatically during system cleanup or reboot.

### 7. /usr

Contains many user applications, libraries, and shared resources.

Important subdirectories:

- `/usr/bin` – Common user commands.
- `/usr/sbin` – System administration commands.
- `/usr/lib` – Libraries.
- `/usr/share` – Architecture-independent shared data.

### 8. /bin

Contains essential user command binaries on traditional Linux systems.

Examples:

```bash
ls
cp
mv
cat
```

On many modern distributions, `/bin` is a symbolic link to `/usr/bin`.

### 9. /sbin

Traditionally contains essential system administration commands.

Examples include:

```bash
ip
fsck
reboot
```

On modern distributions, `/sbin` may link to `/usr/sbin`.

### 10. /boot

Contains files required to boot Linux.

Examples:

- Linux kernel images.
- Initial RAM filesystem (initramfs).
- Bootloader-related files.

### 11. /dev

Contains device files representing hardware and virtual devices.

Examples:

```text
/dev/sda
/dev/null
/dev/zero
/dev/tty
```

### 12. /proc

A virtual filesystem that provides information about running processes and the kernel.

Example:

```bash
cat /proc/cpuinfo
cat /proc/meminfo
```

### 13. /sys

Provides information about devices, drivers, and kernel subsystems.

### 14. /mnt

Commonly used as a temporary mount point for filesystems.

Example:

```bash
sudo mount /dev/sdb1 /mnt
```

### 15. /media

Commonly used for automatically mounted removable devices such as USB drives.

### 16. /opt

Used for optional or third-party software packages.

### 17. /run

Stores temporary runtime information about the system and running processes.

## Quick Reference Table

| Directory | Purpose                           |
| --------- | --------------------------------- |
| `/`       | Root filesystem                   |
| `/home`   | User home directories             |
| `/root`   | Root user's home                  |
| `/etc`    | Configuration files               |
| `/var`    | Logs and changing data            |
| `/tmp`    | Temporary files                   |
| `/usr`    | Applications and shared resources |
| `/bin`    | Essential user commands           |
| `/sbin`   | System administration commands    |
| `/boot`   | Boot-related files                |
| `/dev`    | Device files                      |
| `/proc`   | Process and kernel information    |
| `/sys`    | Device and kernel information     |
| `/mnt`    | Mount point                       |
| `/media`  | Removable media                   |
| `/opt`    | Optional software                 |
| `/run`    | Runtime information               |

## Practical Commands

```bash
ls /
ls /etc
ls /var/log
ls /home
du -sh /var/log
```

## Real-World Use Cases

- Checking application configuration in `/etc`.
- Troubleshooting errors using `/var/log`.
- Finding user files inside `/home`.
- Checking CPU and memory information through `/proc`.
- Mounting additional storage under `/mnt`.

## Summary

Knowing important Linux directories helps administrators locate files quickly, manage applications, troubleshoot errors, and maintain Linux servers.
