# Mount and Umount in Linux

## What is Mounting?

Mounting means making a storage device or filesystem accessible through a directory in Linux.

For example, when you attach a new EBS volume to an AWS EC2 instance, you need to prepare and mount it before using it.

## 1. Check Available Disks

```bash
lsblk
```

This displays attached storage devices and their partitions.

## 2. Create a Mount Directory

Choose a directory where you want to access the storage.

```bash
sudo mkdir -p /mnt/data
```

## 3. Mount a Partition

Example:

```bash
sudo mount /dev/sdb1 /mnt/data
```

Now the filesystem on `/dev/sdb1` is accessible through `/mnt/data`.

## 4. Verify the Mount

```bash
df -h
```

Or:

```bash
lsblk
```

## 5. Access Mounted Storage

```bash
cd /mnt/data
```

Create a test file:

```bash
sudo touch test.txt
```

## 6. Unmount a Filesystem

Before removing or disconnecting storage, unmount it.

```bash
sudo umount /mnt/data
```

You can also unmount using the device name:

```bash
sudo umount /dev/sdb1
```

## 7. Check Mounted Filesystems

```bash
findmnt
```

To check a specific mount point:

```bash
findmnt /mnt/data
```

## 8. Mount Automatically After Reboot

Linux uses `/etc/fstab` to configure filesystems that should be mounted automatically.

First, find the partition UUID:

```bash
sudo blkid /dev/sdb1
```

Edit the configuration:

```bash
sudo nano /etc/fstab
```

Example entry for ext4:

```text
UUID=your-uuid /mnt/data ext4 defaults,nofail 0 2
```

Replace `your-uuid` with the actual UUID.

Test the configuration:

```bash
sudo mount -a
```

If there are no errors, check the mount:

```bash
findmnt /mnt/data
```

**Important:** Incorrect `/etc/fstab` entries can cause boot problems. Always back up the file and test changes before rebooting.

## Important Points

- `mount` makes a filesystem accessible.
- `umount` safely disconnects a mounted filesystem.
- `/mnt` is commonly used for temporary mount points.
- `/etc/fstab` stores persistent mount configuration.
- Unmount filesystems before detaching their storage devices.

## Practice

1. Attach a test EBS volume to an EC2 instance.
2. Identify the new disk using `lsblk`.
3. Create a mount directory.
4. Mount the filesystem.
5. Create a test file.
6. Unmount the filesystem.
