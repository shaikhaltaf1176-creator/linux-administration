# Journalctl in Linux

## What is journalctl?

`journalctl` is a command used to view system logs collected by `systemd-journald`.

It helps administrators investigate system problems, service failures, boot issues, and other events.

For example, if Nginx fails to start, we can use `journalctl` to find the reason.

## 1. View All Available Logs

```bash
sudo journalctl
```

This displays logs stored in the system journal.

## 2. View the Latest Logs

```bash
sudo journalctl -n 50
```

This displays the latest 50 log entries.

## 3. Follow Logs in Real Time

```bash
sudo journalctl -f
```

This continuously displays new log entries.

Press `Ctrl + C` to stop following the logs.

## 4. View Logs for a Specific Service

Example: Nginx.

```bash
sudo journalctl -u nginx
```

On Ubuntu, SSH logs:

```bash
sudo journalctl -u ssh
```

On Amazon Linux, SSH logs:

```bash
sudo journalctl -u sshd
```

## 5. View Recent Service Logs

```bash
sudo journalctl -u nginx -n 50
```

## 6. Follow Service Logs in Real Time

```bash
sudo journalctl -u nginx -f
```

## 7. View Logs from the Current Boot

```bash
sudo journalctl -b
```

View logs from the previous boot, if retained:

```bash
sudo journalctl -b -1
```

## 8. Filter Logs by Time

View logs from today:

```bash
sudo journalctl --since today
```

View logs from the last hour:

```bash
sudo journalctl --since "1 hour ago"
```

View logs between two times:

```bash
sudo journalctl --since "2026-11-03 10:00:00" --until "2026-11-03 12:00:00"
```

## 9. View Error Messages

```bash
sudo journalctl -p err
```

Common priority levels:

| Priority | Meaning       |
| -------- | ------------- |
| `0`      | Emergency     |
| `1`      | Alert         |
| `2`      | Critical      |
| `3`      | Error         |
| `4`      | Warning       |
| `5`      | Notice        |
| `6`      | Informational |
| `7`      | Debug         |

## 10. Check Journal Disk Usage

```bash
sudo journalctl --disk-usage
```

## 11. Remove Old Journal Logs

For example, keep only the last seven days:

```bash
sudo journalctl --vacuum-time=7d
```

This removes older archived journal files, subject to journald's storage configuration.

## Practice

```bash
sudo journalctl -n 20
sudo journalctl -u nginx
sudo journalctl -u nginx -f
sudo journalctl -b
sudo journalctl -p err
sudo journalctl --disk-usage
```

## Important Points

- `journalctl` is used to read systemd journal logs.
- `-u` filters logs by service.
- `-f` follows new log entries.
- `-b` displays logs from a boot.
- `-p err` filters error messages.

Use journalctl whenever you need to investigate system or service problems.
