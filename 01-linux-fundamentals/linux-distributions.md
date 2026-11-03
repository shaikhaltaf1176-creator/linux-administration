# Linux Distributions

## What is a Linux Distribution?

A Linux distribution (Distro) is an operating system built using the Linux kernel along with system utilities, package managers, libraries, and applications.

Different distributions are designed for different purposes.

## Popular Linux Distributions

| Distribution                    | Common Usage                    |
| ------------------------------- | ------------------------------- |
| Ubuntu                          | Beginners, servers, development |
| Amazon Linux                    | AWS EC2 instances               |
| Debian                          | Stable servers                  |
| Red Hat Enterprise Linux (RHEL) | Enterprise environments         |
| Fedora                          | Developers and new technologies |
| Kali Linux                      | Security testing                |
| Linux Mint                      | Desktop users                   |
| CentOS Stream                   | Enterprise Linux development    |

## Types of Linux Distributions

### 1. Debian-based

Examples:

- Ubuntu
- Linux Mint
- Kali Linux

Package manager: `apt`

### 2. Red Hat-based

Examples:

- RHEL
- Fedora
- Rocky Linux
- Amazon Linux

Package managers: `dnf`, `yum`

## Package Management Examples

Ubuntu / Debian:

```bash
sudo apt update
sudo apt upgrade
sudo apt install nginx
```

Amazon Linux:

```bash
sudo dnf update
sudo dnf install nginx
```

## How to Check Your Linux Distribution

```bash
cat /etc/os-release
```

Check the kernel version:

```bash
uname -r
```

## Conclusion

Linux distributions provide different environments for different requirements. Ubuntu and Amazon Linux are particularly useful to learn for cloud and server administration.
