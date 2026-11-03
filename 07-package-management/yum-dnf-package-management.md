# YUM and DNF Package Management

## Introduction

YUM and DNF are package management tools used in RPM-based Linux distributions.

They help administrators install, update, search, and remove software packages.

These tools are commonly used in distributions such as Amazon Linux, RHEL, Fedora, and Rocky Linux.

## What is YUM?

YUM stands for Yellowdog Updater, Modified.

It is a package management tool used in older RPM-based Linux distributions and remains available in some systems.

## What is DNF?

DNF stands for Dandified YUM.

It is the modern successor to YUM and provides improved dependency management and performance.

Amazon Linux 2023 uses DNF as its package manager.

## Common YUM Commands

### 1. Check Available Updates

```bash
sudo yum check-update
```

### 2. Install a Package

```bash
sudo yum install nginx -y
```

### 3. Update Packages

```bash
sudo yum update -y
```

### 4. Remove a Package

```bash
sudo yum remove nginx -y
```

### 5. Search for a Package

```bash
yum search nginx
```

### 6. Display Package Information

```bash
yum info nginx
```

## Common DNF Commands

### 1. Check Package Manager Version

```bash
dnf --version
```

### 2. Install a Package

```bash
sudo dnf install nginx -y
```

### 3. Update Packages

```bash
sudo dnf upgrade -y
```

### 4. Remove a Package

```bash
sudo dnf remove nginx -y
```

### 5. Search for a Package

```bash
dnf search nginx
```

### 6. Display Package Information

```bash
dnf info nginx
```

### 7. List Installed Packages

```bash
dnf list installed
```

### 8. Clean Package Cache

```bash
sudo dnf clean all
```

## Difference Between YUM and DNF

| YUM | DNF |
|---|---|
| Older package manager | Modern package manager |
| Used in older RPM-based systems | Used in modern RPM-based systems |
| Original implementation | Improved successor |
| Example: `yum install nginx` | Example: `dnf install nginx` |

## Practical Example: Install Nginx on Amazon Linux 2023

Update packages:

```bash
sudo dnf update -y
```

Install Nginx:

```bash
sudo dnf install nginx -y
```

Start Nginx:

```bash
sudo systemctl start nginx
```

Enable it at startup:

```bash
sudo systemctl enable nginx
```

Check its status:

```bash
sudo systemctl status nginx
```

## Which Package Manager Should You Use?

| Linux Distribution | Package Manager |
|---|---|
| Ubuntu | APT |
| Debian | APT |
| Amazon Linux 2 | YUM |
| Amazon Linux 2023 | DNF |
| Fedora | DNF |
| RHEL 8 and later | DNF |

## Real-World Use Cases

- Installing software on Amazon EC2.
- Updating Amazon Linux servers.
- Managing server dependencies.
- Installing web servers and development tools.

## Summary

YUM and DNF are package managers used in RPM-based Linux distributions. DNF is the modern successor to YUM and is the default package manager in Amazon Linux 2023.