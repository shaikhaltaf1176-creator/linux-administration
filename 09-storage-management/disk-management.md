# Disk Management in Linux

## Introduction

Disk management in Linux means checking, monitoring, and managing storage devices.

Linux provides several commands to check available disk space, disk usage, and attached storage devices.

## 1. Check Disk Space

Use the `df` command to check available and used disk space.

```bash
df -h
```

The `-h` option displays sizes in a human-readable format, such as GB and MB.

## 2. Check Directory Size

Use `du` to check how much storage a directory uses.

```bash
du -sh /home
```

Check the size of the current directory:

```bash
du -sh .
```

## 3. List Disks and Partitions

Use `lsblk` to display storage devices and their partitions.

```bash
lsblk
```

Display filesystem information too:

```bash
lsblk -f
```

## 4. Display Disk Information

Use `fdisk` to view disk partition information.

```bash
sudo fdisk -l
```

## 5. Check Disk Usage of a Specific Directory

```bash
du -sh /var/log
```

Find the sizes of directories inside the current location:

```bash
du -h --max-depth=1
```

## 6. Check Disk I/O Statistics

Install `sysstat` if needed.

Ubuntu:

```bash
sudo apt install sysstat -y
```

Amazon Linux 2023:

```bash
sudo dnf install sysstat -y
```

Check disk I/O:

```bash
iostat
```

## Important Commands

| Command | Purpose |
|---|---|
| `df -h` | Check disk space |
| `du -sh` | Check directory size |
| `lsblk` | List disks and partitions |
| `fdisk -l` | Display partition information |
| `iostat` | Monitor disk I/O |

## Practice

1. Check available disk space.
2. List all attached disks.
3. Find the size of your home directory.
4. Check the partitions on your Linux machine.