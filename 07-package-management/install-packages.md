# Installing Packages in Linux

## Introduction

Linux provides package managers that make software installation easier.

Instead of downloading software manually, administrators can install applications directly from configured repositories using commands.

The installation command depends on the Linux distribution.

## 1. Install Packages on Ubuntu

Ubuntu uses APT.

Update package information:

```bash
sudo apt update
```

Install Git:

```bash
sudo apt install git -y
```

Install Python:

```bash
sudo apt install python3 -y
```

Install Nginx:

```bash
sudo apt install nginx -y
```

## 2. Install Packages on Amazon Linux

Amazon Linux 2023 uses DNF.

Update packages:

```bash
sudo dnf update -y
```

Install Git:

```bash
sudo dnf install git -y
```

Install Python:

```bash
sudo dnf install python3 -y
```

Install Nginx:

```bash
sudo dnf install nginx -y
```

For Amazon Linux 2, use YUM.

```bash
sudo yum install git -y
```

## 3. Install Multiple Packages

You can install multiple packages using a single command.

Ubuntu:

```bash
sudo apt install git nginx python3 curl -y
```

Amazon Linux 2023:

```bash
sudo dnf install git nginx python3 curl -y
```

## 4. Verify Package Installation

Check Git version:

```bash
git --version
```

Check Python version:

```bash
python3 --version
```

Check Nginx version:

```bash
nginx -v
```

## 5. Install Packages from a Specific Repository

Linux package managers download packages from configured repositories.

Ubuntu repositories can be managed through:

```bash
/etc/apt/sources.list
```

Additional Ubuntu repository configurations may be stored in:

```bash
/etc/apt/sources.list.d/
```

On Amazon Linux, repository configuration is generally managed through DNF or YUM repository files.

## 6. Troubleshooting Package Installation

### Error: Unable to Locate Package

Ubuntu:

```bash
sudo apt update
```

Check whether the package name is correct.

### Error: No Match for Argument

Amazon Linux:

```bash
sudo dnf search package-name
```

Check whether the package is available in your enabled repositories.

### Error: Permission Denied

Use `sudo` when administrative permissions are required.

Example:

```bash
sudo apt install nginx
```

## Practical Lab: Install Git and Nginx

On Ubuntu:

```bash
sudo apt update
sudo apt install git nginx -y
git --version
nginx -v
```

On Amazon Linux 2023:

```bash
sudo dnf update -y
sudo dnf install git nginx -y
git --version
nginx -v
```

## Real-World Use Cases

- Setting up new EC2 instances.
- Installing application dependencies.
- Preparing Linux servers for deployment.
- Installing web servers and development tools.

## Summary

Package installation in Linux depends on the distribution. Ubuntu uses APT, while Amazon Linux 2023 uses DNF. These tools make installing software simple and efficient.