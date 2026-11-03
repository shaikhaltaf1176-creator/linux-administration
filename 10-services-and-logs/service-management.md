# Service Management in Linux

## What is a Service?

A service is a program that runs in the background and performs a particular task.

Services usually run without requiring direct user interaction.

Examples:

- SSH service for remote access.
- Nginx service for web hosting.
- MySQL service for database management.
- Cron service for scheduled tasks.

## 1. Check Installed Services

To view service unit files:

```bash
systemctl list-unit-files --type=service
```

To view currently running services:

```bash
systemctl list-units --type=service --state=running
```

## 2. Check Service Status

Example: Check SSH.

On Ubuntu:

```bash
sudo systemctl status ssh
```

On Amazon Linux:

```bash
sudo systemctl status sshd
```

## 3. Install Nginx

On Ubuntu:

```bash
sudo apt update
sudo apt install nginx -y
```

On Amazon Linux 2023:

```bash
sudo dnf install nginx -y
```

## 4. Start Nginx

```bash
sudo systemctl start nginx
```

Check its status:

```bash
sudo systemctl status nginx
```

## 5. Enable Nginx at Boot

```bash
sudo systemctl enable nginx
```

Now Nginx is configured to start automatically when the system boots.

## 6. Restart Nginx

```bash
sudo systemctl restart nginx
```

This is useful after making changes that require a service restart.

## 7. Stop Nginx

```bash
sudo systemctl stop nginx
```

## 8. Reload Nginx Configuration

```bash
sudo systemctl reload nginx
```

Use this when you change Nginx configuration and want to apply it without a full restart.

## 9. Check Service Logs

```bash
sudo journalctl -u nginx
```

To view the latest logs:

```bash
sudo journalctl -u nginx -n 50
```

## 10. Troubleshoot a Failed Service

If a service fails to start:

1. Check its status.

```bash
sudo systemctl status nginx
```

2. Check its logs.

```bash
sudo journalctl -u nginx -n 50
```

3. Check the service configuration if necessary.

4. Fix the problem and restart the service.

```bash
sudo systemctl restart nginx
```

## Important Points

- Services run in the background.
- `systemctl` is used to manage services on systemd-based systems.
- Always check service status after starting or restarting it.
- Logs help identify why a service failed.

## Practice

1. Install Nginx.
2. Start the Nginx service.
3. Check its status.
4. Enable it at boot.
5. Stop and restart the service.
6. Check its logs.
