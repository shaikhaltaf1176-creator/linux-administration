# Log Management in Linux

## What are Logs?

Logs are records of events that happen inside a Linux system.

They help administrators understand what is happening on a server and troubleshoot problems.

For example, logs can show:

- Successful and failed login attempts.
- Service startup and shutdown events.
- Application errors.
- System warnings.
- Authentication activity.

## 1. Important Log Directory

Most traditional Linux log files are stored in:

```bash
/var/log
```

List available log files:

```bash
ls -lh /var/log
```

## 2. Important Linux Log Files

| Log File            | Purpose                                           |
| ------------------- | ------------------------------------------------- |
| `/var/log/syslog`   | General system messages on Ubuntu                 |
| `/var/log/messages` | General system messages on many RPM-based systems |
| `/var/log/auth.log` | Authentication logs on Ubuntu                     |
| `/var/log/secure`   | Authentication logs on many RPM-based systems     |
| `/var/log/kern.log` | Kernel messages on Ubuntu                         |
| `/var/log/dmesg`    | Kernel and hardware messages                      |

Log file names and availability can vary between distributions.

## 3. Read a Log File

Use `cat`:

```bash
sudo cat /var/log/syslog
```

Use `less` for large files:

```bash
sudo less /var/log/syslog
```

View the last 20 lines:

```bash
sudo tail -n 20 /var/log/syslog
```

## 4. Monitor Logs in Real Time

Use:

```bash
sudo tail -f /var/log/syslog
```

This displays new log entries as they are added.

Press `Ctrl + C` to stop.

## 5. Search for Errors

Use `grep` to find error messages:

```bash
sudo grep -i "error" /var/log/syslog
```

Search authentication logs for failed login attempts on Ubuntu:

```bash
sudo grep -i "failed" /var/log/auth.log
```

On many RPM-based systems:

```bash
sudo grep -i "failed" /var/log/secure
```

## 6. Log Rotation

Log files can become very large over time.

Linux uses a tool called `logrotate` to manage log files.

It can:

- Rotate old logs.
- Compress previous logs.
- Remove old log files.
- Create new log files.

Check the logrotate configuration:

```bash
cat /etc/logrotate.conf
```

View application-specific configurations:

```bash
ls /etc/logrotate.d/
```

## 7. Check System Logs Using journalctl

Modern systemd-based Linux systems also collect logs using journald.

View system logs:

```bash
sudo journalctl
```

View logs for a specific service:

```bash
sudo journalctl -u nginx
```

## 8. Check System Log Activity

Display recent kernel messages:

```bash
sudo dmesg
```

Display recent kernel messages in readable format:

```bash
sudo dmesg -T
```

## Important Points

- Logs record system and application events.
- `/var/log` stores many traditional Linux log files.
- `tail -f` monitors log files in real time.
- `grep` helps search for specific messages.
- `logrotate` controls log file growth.
- `journalctl` displays logs collected by systemd-journald.

## Practice

1. Explore the `/var/log` directory.
2. Read a system log file.
3. Use `tail -f` to monitor a log.
4. Search for error messages using `grep`.
5. Check Nginx logs.
6. Explore the logrotate configuration.

## Real-World Example

When an application on an AWS EC2 instance stops working:

1. Check the application service status.
2. Read its service logs using `journalctl`.
3. Check relevant files inside `/var/log`.
4. Search for error messages.
5. Fix the issue and restart the service.
