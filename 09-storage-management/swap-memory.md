# Swap Memory in Linux

## What is Swap Memory?

Swap is a storage area that Linux can use as an extension of RAM.

When physical memory (RAM) becomes heavily used, Linux may move less-active memory pages to swap space.

Swap can help prevent memory exhaustion, but it is much slower than RAM.

## 1. Check Memory Usage

Use:

```bash
free -h
```

This displays:

- Total RAM
- Used RAM
- Available RAM
- Total swap
- Used swap

## 2. Check Active Swap

```bash
swapon --show
```

You can also check:

```bash
cat /proc/swaps
```

## 3. Create a Swap File

Example: Create a 2 GB swap file.

```bash
sudo fallocate -l 2G /swapfile
```

Set secure permissions:

```bash
sudo chmod 600 /swapfile
```

Format it as swap:

```bash
sudo mkswap /swapfile
```

## 4. Enable Swap

```bash
sudo swapon /swapfile
```

Verify:

```bash
free -h
```

## 5. Make Swap Permanent

To enable swap automatically after reboot, add an entry to `/etc/fstab`.

Open the file:

```bash
sudo nano /etc/fstab
```

Add:

```text
/swapfile none swap sw 0 0
```

Save the file and test it:

```bash
sudo mount -a
```

Then verify:

```bash
swapon --show
```

## 6. Disable Swap

To temporarily disable the swap file:

```bash
sudo swapoff /swapfile
```

## 7. Remove Swap File

First disable it:

```bash
sudo swapoff /swapfile
```

Remove its entry from `/etc/fstab`, then delete the file:

```bash
sudo rm /swapfile
```

## 8. Check Swappiness

Swappiness controls how aggressively Linux uses swap.

Check the current value:

```bash
cat /proc/sys/vm/swappiness
```

Temporarily change it:

```bash
sudo sysctl vm.swappiness=10
```

## Important Points

- Swap provides additional virtual memory support.
- Swap can be created using a partition or a file.
- Swap is slower than physical RAM.
- `free -h` displays memory usage.
- `swapon` enables swap.
- `swapoff` disables swap.

## Practice

1. Check RAM and swap usage.
2. Create a 1 GB swap file on a test machine.
3. Enable the swap file.
4. Verify it using `free -h`.
5. Disable and remove the test swap file.
