# Netstat and SS Commands in Linux

## Introduction

Linux provides networking tools to check active connections, listening ports, and network statistics.

Two commonly used commands are:

- `netstat` – Traditional networking command.
- `ss` – Modern replacement for many netstat features.

## 1. The netstat Command

### Install netstat

Ubuntu:

```bash
sudo apt install net-tools -y
```

Amazon Linux 2023:

```bash
sudo dnf install net-tools -y
```

### Display Network Connections

```bash
netstat
```

### Show Listening Ports

```bash
netstat -tuln
```

### Show Process Information

```bash
sudo netstat -tulnp
```

### Display Routing Table

```bash
netstat -r
```

## 2. The ss Command

The `ss` command displays socket information and is generally preferred on modern Linux systems.

### Display All Connections

```bash
ss -a
```

### Show Listening Ports

```bash
ss -tuln
```

### Show TCP Connections

```bash
ss -t
```

### Show UDP Connections

```bash
ss -u
```

### Show Listening Ports with Process Information

```bash
sudo ss -tulnp
```

### Check a Specific Port

```bash
sudo ss -tulnp | grep :22
```

This checks whether a process is listening on port 22.

## 3. Understand Common Options

| Option | Meaning                          |
| ------ | -------------------------------- |
| `-t`   | TCP connections                  |
| `-u`   | UDP connections                  |
| `-l`   | Listening sockets                |
| `-n`   | Show numeric addresses and ports |
| `-p`   | Show process information         |
| `-a`   | Show all sockets                 |

## Difference Between netstat and ss

| netstat                  | ss                            |
| ------------------------ | ----------------------------- |
| Traditional tool         | Modern tool                   |
| Comes from net-tools     | Usually provided by iproute2  |
| May need installation    | Commonly available by default |
| Older networking utility | Recommended for modern Linux  |

## Practice

```bash
ss -tuln
sudo ss -tulnp
ss -t
ss -u
netstat -r
```

These commands are especially useful when checking whether an application is listening on the expected port.
