# Linux Process Management Basics

## Introduction

A process is a program that is currently running on a Linux system.

Whenever you open an application, execute a command, or start a service, Linux creates a process to handle that task.

Linux allows multiple processes to run at the same time. Process management helps administrators monitor, control, and manage these running programs.

## What is a Process?

A process is an instance of a running program.

For example:

- Running `python app.py` creates a process.
- Starting an Nginx service creates a process.
- Opening a terminal creates a shell process.

## Important Process Terms

### 1. PID (Process ID)

Every process gets a unique Process ID (PID).

Check running processes:

```bash
ps
```

### 2. PPID (Parent Process ID)

PPID identifies the parent process that started another process.

```bash
ps -ef
```

### 3. Parent Process

A parent process is responsible for creating another process.

### 4. Child Process

A child process is created by another process.

### 5. Daemon Process

A daemon is a background process that usually provides services without direct user interaction.

Examples:
- SSH service
- Cron service
- Web server

## Process States

Linux processes can have different states.

| State | Meaning |
|---|---|
| R | Running or ready to run |
| S | Interruptible sleep |
| D | Uninterruptible sleep |
| T | Stopped or traced |
| Z | Zombie process |
| I | Idle kernel thread |

## Viewing Process Information

Display running processes:

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

Display process hierarchy:

```bash
pstree
```

## Understanding PID 1

The first userspace process started by Linux is normally `systemd`.

Check it:

```bash
ps -p 1 -o pid,comm
```

Output:

```text
PID  COMMAND
1    systemd
```

Systemd manages system services and other processes.

## Foreground vs Background Processes

- Foreground process: Runs directly in the terminal and may occupy it until completion.
- Background process: Runs without keeping the terminal occupied.

Example:

```bash
sleep 100 &
```

The `&` symbol starts the command in the background.

## Real-World Use Cases

- Monitoring running applications.
- Troubleshooting high CPU usage.
- Checking whether a service is running.
- Identifying unwanted processes.
- Managing applications on AWS EC2 instances.

## Summary

Process management helps Linux administrators monitor and control running programs. Understanding PID, PPID, process states, and background processes is important for managing Linux servers.