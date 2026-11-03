# Systemd in Linux

## What is Systemd?

Systemd is the system and service manager used by many modern Linux distributions.

It starts and manages system services during boot and helps keep the system running.

For example, when a Linux server starts, systemd can automatically start services such as SSH, networking, and Nginx.

## 1. Main Responsibilities of Systemd

- Starts services during system boot.
- Manages background services.
- Monitors system processes.
- Handles system startup and shutdown.
- Manages system logs through journald.
- Controls service dependencies.

## 2. What is a Service?

A service is a background program that performs a specific task.

Examples:

- SSH – Allows remote server access.
- Nginx – Runs a web server.
- MySQL – Manages databases.
- Docker – Manages containers.

Systemd manages many of these services.

## 3. Systemd Unit Files

Systemd uses unit files to define how different resources should be managed.

Common unit types:

| Unit | Purpose |
|---|---|
| `.service` | Manages services |
| `.socket` | Manages sockets |
| `.timer` | Schedules tasks |
| `.mount` | Manages mount points |
| `.target` | Groups units together |

## 4. Check Systemd Version

```bash
systemctl --version
```

## 5. Check the Default Boot Target

```bash
systemctl get-default
```

Common targets:

- `multi-user.target` – Multi-user system without a graphical desktop.
- `graphical.target` – Multi-user system with a graphical desktop.

## 6. View Systemd Units

```bash
systemctl list-units
```

List all installed unit files:

```bash
systemctl list-unit-files
```

## Important Points

- Systemd manages services and system startup.
- Unit files define how resources are managed.
- `systemctl` is the main command used to interact with systemd.
- Many modern Linux distributions use systemd.

## Practice

1. Check the systemd version.
2. Find your default boot target.
3. List running systemd units.
4. Find installed service unit files.