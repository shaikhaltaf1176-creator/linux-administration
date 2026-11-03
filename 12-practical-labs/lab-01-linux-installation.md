# Lab 01: Linux Installation

## Objective

Install Linux and understand the basic operating system environment.

## Requirements

- Windows computer or laptop.
- Internet connection.
- VirtualBox or VMware.
- Ubuntu ISO image.

## Step 1: Download Ubuntu

Download Ubuntu Desktop from:

https://ubuntu.com/download/desktop

Download and install VirtualBox:

https://www.virtualbox.org/

## Step 2: Create a Virtual Machine

1. Open VirtualBox.
2. Click **New**.
3. Enter the name: `Ubuntu-Linux`.
4. Select Linux as the operating system.
5. Choose Ubuntu (64-bit).
6. Allocate RAM and CPU resources.
7. Create a virtual hard disk.

Recommended starting configuration:

| Resource | Recommended |
|---|---|
| RAM | 4 GB |
| CPU | 2 cores |
| Disk | 25 GB |
| OS | Ubuntu |

Adjust resources according to your computer's available capacity.

## Step 3: Install Ubuntu

1. Select the downloaded Ubuntu ISO file.
2. Start the virtual machine.
3. Select **Install Ubuntu**.
4. Choose language and keyboard layout.
5. Select the installation type.
6. Create your username and password.
7. Complete the installation.
8. Restart the virtual machine.

## Step 4: Update Linux

Open the terminal and run:

```bash
sudo apt update
sudo apt upgrade -y
```

## Step 5: Check System Information

```bash
uname -a
hostname
whoami
pwd
```

## Step 6: Check Linux Version

```bash
cat /etc/os-release
```

## Step 7: Check Memory and Storage

```bash
free -h
df -h
lsblk
```

## Verification

Confirm that:

- Ubuntu starts successfully.
- You can log in.
- Terminal commands work.
- Internet connectivity is available.
- System information is displayed.

## Expected Result

Ubuntu Linux is successfully installed and ready for practice.

## What I Learned

- How to install Linux using a virtual machine.
- How to access the Linux terminal.
- How to update packages.
- How to check system information and resources.