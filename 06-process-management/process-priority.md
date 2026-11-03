# Linux Process Priority – nice and renice

## Introduction

Linux can run multiple processes at the same time, but not every process needs the same amount of CPU attention.

Process priority helps Linux decide which processes should receive CPU time more favorably.

Linux provides two important commands for managing process priority:

1. `nice`
2. `renice`

## 1. What is Process Priority?

Process priority influences how the Linux scheduler allocates CPU time to processes.

Linux uses a nice value to influence the scheduling priority of normal processes.

Nice values range from:

```text
-20 to +19
```

| Nice Value | Meaning |
|---|---|
| -20 | Highest scheduling priority |
| 0 | Default priority |
| +19 | Lowest scheduling priority |

A lower nice value generally means a process gets more favorable CPU scheduling.

## 2. nice Command

The `nice` command starts a new process with a specified nice value.

### Basic Syntax

```bash
nice -n VALUE command
```

### Examples

Start a process with the default nice value:

```bash
nice sleep 100
```

Start a process with a nice value of 10:

```bash
nice -n 10 sleep 100
```

Start a process with a higher scheduling priority:

```bash
sudo nice -n -10 sleep 100
```

Setting negative nice values generally requires elevated privileges.

## 3. renice Command

The `renice` command changes the nice value of an already running process.

### Basic Syntax

```bash
renice VALUE -p PID
```

### Example

Find the process ID:

```bash
pgrep -a sleep
```

Change its nice value:

```bash
renice 10 -p 1234
```

Replace `1234` with the actual PID.

## 4. Check Process Priority

Use:

```bash
ps -l
```

Or:

```bash
ps -o pid,ni,pri,comm -p 1234
```

Important columns:

| Column | Meaning |
|---|---|
| PID | Process ID |
| NI | Nice value |
| PRI | Scheduling priority |
| COMMAND | Process name |

## 5. Difference Between nice and renice

| nice | renice |
|---|---|
| Starts a new process with a nice value | Changes an existing process's nice value |
| Used before or during process startup | Used after the process has started |
| Example: `nice -n 10 command` | Example: `renice 10 -p 1234` |

## 6. Practical Example

Start a background process with a nice value of 10:

```bash
nice -n 10 sleep 300 &
```

Find its PID:

```bash
pgrep -a sleep
```

Check its priority:

```bash
ps -o pid,ni,pri,comm -p PID
```

Change its nice value:

```bash
renice 15 -p PID
```

Replace `PID` with the actual process ID.

## Real-World Use Cases

- Running backup tasks with lower CPU scheduling priority.
- Managing resource-intensive applications.
- Preventing background tasks from competing as aggressively with important workloads.
- Managing CPU scheduling on Linux servers.

## Important Note

Nice values influence CPU scheduling priority, but they do not guarantee a fixed amount of CPU time or prevent a process from using CPU resources.

## Summary

The `nice` command starts a process with a selected nice value, while `renice` changes the nice value of an existing process. These commands help administrators influence CPU scheduling on Linux systems.