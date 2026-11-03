# Lab 06: Storage Management in Linux

## Objective

Learn how to identify disks, create partitions, format filesystems, mount storage, and check disk usage.

## Requirements

- Ubuntu or Amazon Linux EC2 instance.
- One additional empty EBS volume.
- Sudo privileges.

**Important:** Use a new empty test volume. The following partitioning and formatting steps can destroy existing data.

## Step 1: Attach an EBS Volume

1. Open the AWS EC2 Console.
2. Navigate to **Elastic Block Store → Volumes**.
3. Create a new EBS volume in the same Availability Zone as your EC2 instance.
4. Attach it to your EC2 instance.

## Step 2: Identify the New Disk

Connect to the EC2 instance and run:

```bash
lsblk
```

Identify the newly attached disk.

Example:

```text
NAME        SIZE TYPE
nvme0n1      8G disk
├─nvme0n1p1  8G part
nvme1n1      5G disk
```

In this example, `/dev/nvme1n1` is the additional disk.

Your actual device name may be different.

## Step 3: Create a Partition

Use the actual device name from `lsblk`.

```bash
sudo fdisk /dev/nvme1n1
```

Inside fdisk:

- Press `n` to create a new partition.
- Press `p` if prompted for a primary partition.
- Accept the default partition number and available size.
- Press `w` to save the changes.

Refresh and check:

```bash
sudo partprobe /dev/nvme1n1
lsblk
```

## Step 4: Create a Filesystem

Identify the new partition.

Example:

```bash
sudo mkfs.ext4 /dev/nvme1n1p1
```

Replace the example device name with your actual partition.

## Step 5: Create a Mount Directory

```bash
sudo mkdir -p /mnt/data
```

## Step 6: Mount the Partition

```bash
sudo mount /dev/nvme1n1p1 /mnt/data
```

## Step 7: Verify the Mount

```bash
df -h
lsblk -f
```

## Step 8: Create a Test File

```bash
sudo touch /mnt/data/test.txt
```

Verify:

```bash
ls -l /mnt/data
```

## Step 9: Configure Automatic Mounting

Find the filesystem UUID:

```bash
sudo blkid /dev/nvme1n1p1
```

Back up the existing configuration:

```bash
sudo cp /etc/fstab /etc/fstab.backup
```

Edit:

```bash
sudo nano /etc/fstab
```

Add the following entry using your actual UUID:

```text
UUID=YOUR-UUID /mnt/data ext4 defaults,nofail 0 2
```

Test the configuration:

```bash
sudo mount -a
```

Check:

```bash
findmnt /mnt/data
```

## Step 10: Unmount the Volume

```bash
sudo umount /mnt/data
```

Verify:

```bash
lsblk
```

## Step 11: Check Disk Usage

```bash
df -h
du -sh /mnt/data
```

The directory may show zero usage after unmounting because the test filesystem is no longer mounted there.

## Cleanup

After completing the lab:

1. Unmount the filesystem.
2. Detach the EBS volume from EC2.
3. Delete the test volume if you no longer need it.

Only delete the volume after confirming that it contains no important data.

## Expected Result

You successfully attached an EBS volume, created a partition, formatted it, mounted it, and configured automatic mounting.

## What I Learned

- Identifying storage devices.
- Creating disk partitions.
- Formatting filesystems.
- Mounting and unmounting storage.
- Configuring `/etc/fstab`.
- Managing AWS EBS storage.
