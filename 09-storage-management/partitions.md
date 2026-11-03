# Disk Partitions in Linux

## What is a Partition?

A partition is a logical section of a physical storage device.

A single disk can be divided into multiple partitions. Each partition can be used for a different purpose.

For example, a Linux server may have separate partitions for:

- Root directory (`/`)
- Home directory (`/home`)
- Boot files (`/boot`)
- Swap space

## 1. View Existing Partitions

Use:

```bash
lsblk
```

For detailed partition information:

```bash
sudo fdisk -l
```

## 2. Understand Disk Names

Linux identifies storage devices using names such as:

```text
/dev/sda
/dev/sdb
/dev/nvme0n1
```

Partitions may look like:

```text
/dev/sda1
/dev/sda2
/dev/nvme0n1p1
```

The exact naming depends on the storage device.

## 3. Create a Partition Using fdisk

**Warning:** Partitioning can destroy existing data. Use an empty test disk or a disposable virtual machine.

First, identify the correct disk:

```bash
lsblk
```

Open the partition tool:

```bash
sudo fdisk /dev/sdb
```

Inside fdisk, common options include:

| Option | Purpose                     |
| ------ | --------------------------- |
| `m`    | Display help                |
| `p`    | Print partition table       |
| `n`    | Create a new partition      |
| `d`    | Delete a partition          |
| `w`    | Write changes and exit      |
| `q`    | Exit without saving changes |

After creating a partition, verify it:

```bash
lsblk
```

## 4. Refresh the Partition Table

If required, ask Linux to reread the partition table:

```bash
sudo partprobe /dev/sdb
```

## 5. Understand GPT and MBR

Two common partition table formats are:

### MBR (Master Boot Record)

- Older partitioning format.
- Supports disks up to approximately 2 TB.
- Supports up to four primary partitions.

### GPT (GUID Partition Table)

- Modern partitioning format.
- Supports much larger disks.
- Supports many partitions.
- Commonly used with modern systems.

## Important Points

- A partition divides a disk into logical sections.
- `fdisk` is used to manage partitions.
- `lsblk` displays disks and partitions.
- GPT is the modern partition table format.
- Always back up important data before changing partitions.

## Practice

1. Run `lsblk`.
2. Identify your root disk.
3. Check the partition table using `fdisk -l`.
4. Practice partition creation on a disposable test disk.
