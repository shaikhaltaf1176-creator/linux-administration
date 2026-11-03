# Systemctl in Linux

## What is systemctl?

`systemctl` is the command-line tool used to communicate with systemd.

It helps us start, stop, restart, enable, disable, and check the status of services.

For example, we can use `systemctl` to manage the Nginx web server.

## 1. Check Service Status

```bash
sudo systemctl status nginx
```

This displays whether Nginx is running, stopped, or has failed.

## 2. Start a Service

```bash
sudo systemctl start nginx
```

This starts Nginx immediately.

## 3. Stop a Service

```bash
sudo systemctl stop nginx
```

This stops the running service.

## 4. Restart a Service

```bash
sudo systemctl restart nginx
```

This stops and starts the service again.

## 5. Reload a Service

```bash
sudo systemctl reload nginx
```

Reload asks the service to apply configuration changes without a full restart, if supported.

## 6. Enable a Service

```bash
sudo systemctl enable nginx
```

This configures Nginx to start automatically during boot.

## 7. Disable a Service

```bash
sudo systemctl disable nginx
```

This prevents Nginx from starting automatically during boot.

It does not necessarily stop a service that is already running.

## 8. Enable and Start Together

```bash
sudo systemctl enable --now nginx
```

This enables Nginx at boot and starts it immediately.

## 9. Disable and Stop Together

```bash
sudo systemctl disable --now nginx
```

This disables automatic startup and stops the service.

## 10. List Running Services

```bash
systemctl list-units --type=service --state=running
```

## 11. Check Failed Services

```bash
systemctl --failed
```

## 12. Check Whether a Service Is Enabled

```bash
systemctl is-enabled nginx
```

## Common systemctl Commands

| Command      | Purpose                          |
| ------------ | -------------------------------- |
| `start`      | Start a service                  |
| `stop`       | Stop a service                   |
| `restart`    | Restart a service                |
| `reload`     | Reload configuration             |
| `status`     | Check service status             |
| `enable`     | Start automatically at boot      |
| `disable`    | Disable automatic startup        |
| `is-active`  | Check whether service is active  |
| `is-enabled` | Check whether service is enabled |

## Practice

Try these commands with Nginx:

```bash
sudo systemctl start nginx
sudo systemctl status nginx
sudo systemctl restart nginx
sudo systemctl enable nginx
sudo systemctl stop nginx
```

## Important Note

Starting a service and enabling a service are different:

- `start` runs the service now.
- `enable` configures it to start automatically during boot.
