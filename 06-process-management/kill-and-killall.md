# Linux Process Control – kill and killall

## Introduction

Sometimes a Linux application becomes unresponsive or consumes too many system resources.

Linux provides commands such as `kill` and `killall` to send signals to running processes.

These commands are commonly used to stop, restart, or control processes.

## 1. kill Command

The `kill` command sends a signal to a process using its Process ID (PID).

### Basic Syntax

```bash
kill [signal] PID
```

### Find the Process ID

```bash
ps aux
```

You can also search for a specific process:

```bash
pgrep nginx
```

### Stop a Process

```bash
kill 1234
```

This sends the default `SIGTERM` signal, asking the process to terminate gracefully.

### Forcefully Stop a Process

```bash
kill -9 1234
```

This sends `SIGKILL`, which forces the kernel to terminate the process.

Use this only when normal termination fails.

## 2. Common Linux Signals

| Signal | Number | Purpose |
|---|---|---|
| SIGHUP | 1 | Hangup; often used to reload services |
| SIGINT | 2 | Interrupt a process |
| SIGKILL | 9 | Forcefully terminate a process |
| SIGTERM | 15 | Request graceful termination |
| SIGSTOP | 19 | Stop a process |
| SIGCONT | 18 | Continue a stopped process |

List available signals:

```bash
kill -l
```

## 3. killall Command

The `killall` command sends a signal to processes by their name.

### Basic Syntax

```bash
killall process_name
```

Example:

```bash
killall firefox
```

This requests termination of processes named `firefox`.

Forcefully terminate them:

```bash
killall -9 firefox
```

## 4. Difference Between kill and killall

| kill | killall |
|---|---|
| Uses PID | Uses process name |
| Targets a specific process ID | Targets matching processes |
| Example: `kill 1234` | Example: `killall nginx` |

## 5. Practical Example

Start a test process:

```bash
sleep 500 &
```

Find its PID:

```bash
pgrep -a sleep
```

Stop the process gracefully:

```bash
kill PID
```

Replace `PID` with the actual process ID.

Verify that it stopped:

```bash
pgrep -a sleep
```

## Important Notes

- Prefer `SIGTERM` before using `SIGKILL`.
- Be careful when using `killall`, because it can affect multiple processes.
- Avoid terminating important system processes.
- You may need `sudo` to terminate processes owned by another user.

## Real-World Use Cases

- Stopping unresponsive applications.
- Terminating unwanted background processes.
- Troubleshooting high resource usage.
- Managing processes on Linux servers.

## Summary

The `kill` command controls processes using their PID, while `killall` targets processes by name. Both commands help administrators manage running applications.