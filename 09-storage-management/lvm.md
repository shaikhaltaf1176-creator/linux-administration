# LVM in Linux

## What is LVM?

LVM stands for Logical Volume Manager.

It is a Linux storage management system that allows us to manage disk space more flexibly than traditional partitions.

With LVM, we can combine multiple physical storage devices and create logical volumes from them.

## 1. Basic LVM Components

LVM has three main components:

### Physical Volume (PV)

A physical disk or partition prepared for LVM.

Example:

```text
/dev/sdb1
```

### Volume Group (VG)

A storage pool created from one or more physical volumes.

Example:

```text
my_vg
```

### Logical Volume (LV)

A virtual storage device created from a volume group.

Example:

```text
my_lv
```

## 2. Understand the LVM Structure

```text
Physical Volume (PV)
        |
        v
Volume Group (VG)
        |
        v
Logical Volume (LV)
        |
        v
Filesystem
        |
        v
Mount Point
```

## 3. Install LVM Tools

Ubuntu:

```bash
sudo apt update
sudo apt install lvm2 -y
```

Amazon Linux 2023:

```bash
sudo dnf install lvm2 -y
```

## 4. Create a Physical Volume

First, identify an empty test disk or partition:

```bash
lsblk
```

Prepare the partition for LVM:

```bash
sudo pvcreate /dev/sdb1
```

Check physical volumes:

```bash
sudo pvs
```

## 5. Create a Volume Group

```bash
sudo vgcreate my_vg /dev/sdb1
```

Check volume groups:

```bash
sudo vgs
```

## 6. Create a Logical Volume

Create a logical volume of 5 GB:

```bash
sudo lvcreate -L 5G -n my_lv my_vg
```

Check logical volumes:

```bash
sudo lvs
```

## 7. Create a Filesystem

Create an ext4 filesystem:

```bash
sudo mkfs.ext4 /dev/my_vg/my_lv
```

## 8. Mount the Logical Volume

Create a directory:

```bash
sudo mkdir -p /mnt/lvm
```

Mount the volume:

```bash
sudo mount /dev/my_vg/my_lv /mnt/lvm
```

Verify:

```bash
df -h
```

## 9. Extend a Logical Volume

If the volume group has free space, increase the logical volume size.

Example: Add 2 GB.

```bash
sudo lvextend -L +2G -r /dev/my_vg/my_lv
```

The `-r` option also resizes the supported filesystem.

## Important LVM Commands

| Command    | Purpose                      |
| ---------- | ---------------------------- |
| `pvcreate` | Create a physical volume     |
| `pvs`      | Display physical volumes     |
| `vgcreate` | Create a volume group        |
| `vgs`      | Display volume groups        |
| `lvcreate` | Create a logical volume      |
| `lvs`      | Display logical volumes      |
| `lvextend` | Increase logical volume size |

## Important Points

- PV represents physical storage prepared for LVM.
- VG combines physical volumes into a storage pool.
- LV provides usable logical storage.
- LVM makes storage expansion and management more flexible.
- Always check available space before extending a volume.

## Practice

Use a disposable Linux virtual machine with an empty test disk.

1. Create a physical volume.
2. Create a volume group.
3. Create a logical volume.
4. Format it with ext4.
5. Mount it.
6. Practice extending the logical volume.

**Warning:** LVM operations on the wrong disk or partition can cause data loss.
