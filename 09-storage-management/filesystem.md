# Filesystem in Linux

## What is a Filesystem?

A filesystem is the method Linux uses to organize and store data on a storage device.

It helps the operating system manage files, directories, permissions, and available storage space.

Before using a newly created partition to store files, we generally need to create a filesystem on it.

## 1. Common Linux Filesystems

| Filesystem | Description                              |
| ---------- | ---------------------------------------- |
| ext4       | Common Linux filesystem                  |
| XFS        | High-performance filesystem              |
| Btrfs      | Supports snapshots and advanced features |
| FAT32      | Commonly used on removable storage       |
| NTFS       | Commonly used by Windows                 |

## 2. Check Existing Filesystems

Use:

```bash
lsblk -f
```

You can also use:

```bash
df -Th
```

These commands show filesystem types and mounted storage.

## 3. Create an ext4 Filesystem

**Warning:** Formatting a partition erases its existing data. Make sure you select the correct empty test partition.

Example:

```bash
sudo mkfs.ext4 /dev/sdb1
```

This creates an ext4 filesystem on `/dev/sdb1`.

## 4. Create an XFS Filesystem

```bash
sudo mkfs.xfs /dev/sdb1
```

This creates an XFS filesystem.

## 5. Check Filesystem Information

```bash
sudo blkid
```

To check a specific partition:

```bash
sudo blkid /dev/sdb1
```

## 6. Check Filesystem Disk Usage

```bash
df -hT
```

This displays mounted filesystems, their types, and disk usage.

## 7. Check and Repair Filesystems

For ext4 filesystems, use `fsck` when the filesystem is unmounted.

```bash
sudo fsck /dev/sdb1
```

For XFS filesystems, use:

```bash
sudo xfs_repair /dev/sdb1
```

Do not run filesystem repair commands on a mounted filesystem. Follow the appropriate recovery procedure for the filesystem.

## Important Points

- A filesystem organizes data on a partition.
- ext4 and XFS are commonly used in Linux.
- `mkfs` creates a filesystem.
- `blkid` displays filesystem information.
- Formatting a partition removes existing data.

## Practice

1. Check your filesystem types.
2. Identify your root filesystem.
3. Explore `lsblk -f` and `df -Th`.
4. Create an ext4 filesystem on a disposable test partition.
