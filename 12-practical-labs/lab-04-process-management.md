# Lab 04: Process Management in Linux

## Objective

Learn how to view, monitor, and manage running processes in Linux.

## Requirements

- Ubuntu or Amazon Linux.
- Terminal access.

## Step 1: View Running Processes

```bash
ps aux
```

This displays running processes and their details.

## Step 2: Search for a Process

```bash
ps aux | grep nginx
```

This searches for processes containing `nginx` in their command information.

## Step 3: Monitor Processes

```bash
top
```

This displays real-time information about CPU, memory, and processes.

Press `q` to exit.

## Step 4: Run a Background Process

Start a command in the background:

```bash
sleep 300 &
```

The `&` symbol runs the command in the background.

## Step 5: Check Background Jobs

```bash
jobs
```

Display the process ID:

```bash
pgrep -a sleep
```

## Step 6: Stop a Process

Find the process ID:

```bash
pgrep -a sleep
```

Stop the process using its PID:

```bash
kill PID
```

Replace `PID` with the actual process ID.

## Step 7: Forcefully Stop a Process

If a process does not stop normally:

```bash
kill -9 PID
```

Use `kill -9` only when necessary because it does not allow the process to clean up.

## Step 8: Check Process Priority

```bash
ps -eo pid,ni,comm
```

Start a process with a lower scheduling priority:

```bash
nice -n 10 sleep 300 &
```

## Step 9: Change Process Priority

```bash
sudo renice 5 -p PID
```

Replace `PID` with the process ID.

## Verification

```bash
ps aux
top
pgrep -a sleep
```

Confirm that you can identify and stop the test process.

## Expected Result

You successfully viewed, monitored, started, and stopped Linux processes.

## What I Learned

- Understanding processes and PIDs.
- Using `ps` and `top`.
- Running background processes.
- Stopping processes with `kill`.
- Managing process priority.
