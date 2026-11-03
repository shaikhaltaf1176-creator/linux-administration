# IP and ifconfig Commands in Linux

## Introduction

Linux provides commands to view and manage network interfaces and IP addresses.

Two commonly used commands are:

- `ip` – Modern command for network management.
- `ifconfig` – Older command used to view and configure network interfaces.

## 1. The ip Command

The `ip` command is the modern tool for managing network settings.

### Display IP Addresses

```bash
ip addr
```

Or:

```bash
ip a
```

### Show Network Interfaces

```bash
ip link show
```

### Display Routing Information

```bash
ip route
```

### Bring an Interface Up

```bash
sudo ip link set eth0 up
```

### Bring an Interface Down

```bash
sudo ip link set eth0 down
```

Replace `eth0` with your actual interface name.

### Display a Specific Interface

```bash
ip addr show eth0
```

## 2. The ifconfig Command

`ifconfig` is an older Linux networking command.

It may not be installed by default on modern Linux distributions.

### Display Network Information

```bash
ifconfig
```

### Display All Interfaces

```bash
ifconfig -a
```

### Enable an Interface

```bash
sudo ifconfig eth0 up
```

### Disable an Interface

```bash
sudo ifconfig eth0 down
```

## 3. Install ifconfig

On Ubuntu:

```bash
sudo apt update
sudo apt install net-tools -y
```

On Amazon Linux 2023:

```bash
sudo dnf install net-tools -y
```

## Difference Between ip and ifconfig

| ip                                    | ifconfig                       |
| ------------------------------------- | ------------------------------ |
| Modern command                        | Older command                  |
| Usually installed by default          | May need installation          |
| Supports modern networking features   | Limited compared to ip         |
| Recommended for current Linux systems | Mainly used in older tutorials |

## Practice

Run these commands and compare their outputs:

```bash
ip addr
ip route
ip link show
ifconfig
```
