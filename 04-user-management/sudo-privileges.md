# Linux Sudo Privileges

## Overview
`sudo` stands for Superuser Do. It allows authorized users to execute commands with elevated privileges, usually as the root user.

It helps administrators perform system-level operations without logging in directly as root.

## Sudo Commands

| Command | Description |
|---|---|
| `sudo command` | Executes a command with elevated privileges |
| `sudo -i` | Opens a root login shell |
| `sudo -l` | Lists allowed sudo commands |
| `sudo -u user` | Executes a command as another user |
| `visudo` | Safely edits the sudoers configuration |
| `su -` | Switches to the root user |

## Practical Examples

### 1. Execute a command using sudo

```bash
sudo apt update
```

### 2. Check sudo permissions

```bash
sudo -l
```

### 3. Switch to the root shell

```bash
sudo -i
```

### 4. Add a user to the sudo group (Ubuntu)

```bash
sudo usermod -aG sudo altaf
```

### 5. Add a user to the wheel group (Amazon Linux)

```bash
sudo usermod -aG wheel altaf
```

### 6. Edit sudoers configuration

```bash
sudo visudo
```

### 7. Verify user group membership

```bash
groups altaf
```

## Important Concepts

### Root User
The root user is the administrator account with full system privileges.

### Sudo Group
On Ubuntu, members of the `sudo` group can execute authorized administrative commands.

### Wheel Group
On Amazon Linux and many other distributions, the `wheel` group is commonly used to grant sudo access.

### Sudoers File
The `/etc/sudoers` file defines which users and groups can execute commands with elevated privileges.

## Important Note
Always use `visudo` to modify sudoers configuration. It checks the syntax before saving and helps prevent configuration errors.

## Learning Outcome
Learned how to provide administrative access, check sudo permissions, and manage privileged commands in Linux.