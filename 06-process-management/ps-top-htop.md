# Linux Process Monitoring – ps, top, and htop

## Introduction

Linux provides several commands to monitor running processes and system resource usage.

The most commonly used commands are:

- `ps`
- `top`
- `htop`

These commands help administrators understand which processes are running and how much CPU and memory they are consuming.

## 1. ps Command

The `ps` command displays information about running processes.

### Basic Usage

Display processes running in the current terminal:

```bash
ps
```

Display all processes:

```bash
ps aux
```

Display processes in full format:

```bash
ps -ef
```

### Important Options

| Option | Purpose |
|---|---|
| `-a` | Show processes associated with terminals |
| `-u` | Display user-oriented information |
| `-x` | Include processes without a controlling terminal |
| `-e` | Display all processes |
| `-f` | Show full-format information |

### Find a Specific Process

```bash
ps aux | grep nginx
```

This searches the process list for Nginx.

## 2. top Command

The `top` command displays live system and process information.

```bash
top
```

It shows:
- CPU usage.
- Memory usage.
- Running processes.
- Process IDs.
- Load average.

### Useful top Shortcuts

| Key | Purpose |
|---|---|
| P | Sort by CPU usage |
| M | Sort by memory usage |
| k | Send a signal to a process |
| q | Exit top |
| 1 | Show individual CPU information |

## 3. htop Command

`htop` is an interactive process monitoring tool with a more user-friendly interface.

Install on Ubuntu:

```bash
sudo apt update
sudo apt install htop -y
```

Install on Amazon Linux 2023:

```bash
sudo dnf install htop -y
```

Start htop:

```bash
htop
```

It provides:
- Color-coded CPU usage.
- Memory and swap usage.
- Process filtering.
- Process sorting.
- Interactive process management.

## Difference Between ps, top, and htop

| Command | Purpose |
|---|---|
| `ps` | Displays a snapshot of processes |
| `top` | Displays live process information |
| `htop` | Interactive and user-friendly process monitoring |

## Practical Examples

Find the Nginx process:

```bash
ps aux | grep nginx
```

Monitor system resources:

```bash
top
```

Monitor processes interactively:

```bash
htop
```

Check a process using its PID:

```bash
ps -p 1234
```

Replace `1234` with the actual process ID.

## Real-World Use Cases

- Finding applications consuming high CPU.
- Monitoring memory usage.
- Checking whether an application is running.
- Troubleshooting slow Linux servers.
- Monitoring EC2 instance performance.

## Summary

`ps` provides a process snapshot, while `top` and `htop` help monitor processes continuously. These commands are essential for Linux system monitoring and troubleshooting.