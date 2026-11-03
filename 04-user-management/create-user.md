# Linux User Management

## Overview
Linux allows administrators to create, modify, delete, and manage user accounts. Each user has a separate username, user ID (UID), home directory, and permissions.

## User Management Commands

| Command | Description |
|---|---|
| `whoami` | Displays the current user |
| `who` | Shows logged-in users |
| `id` | Displays user and group IDs |
| `useradd` | Creates a new user |
| `adduser` | Creates a user interactively (Ubuntu) |
| `passwd` | Sets or changes a password |
| `usermod` | Modifies an existing user |
| `userdel` | Deletes a user |
| `su` | Switches to another user |
| `getent passwd` | Displays user account information |

## Practical Examples

### 1. Create a user

```bash
sudo useradd altaf
```

### 2. Set a password

```bash
sudo passwd altaf
```

### 3. Create a user with a home directory

```bash
sudo useradd -m rahul
```

### 4. Modify a username

```bash
sudo usermod -l newname rahul
```

### 5. Delete a user

```bash
sudo userdel altaf
```

### 6. Delete a user with their home directory

```bash
sudo userdel -r rahul
```

### 7. Switch to another user

```bash
su - altaf
```

### 8. Check user information

```bash
id altaf
```

## Important Files

| File | Purpose |
|---|---|
| `/etc/passwd` | Stores user account information |
| `/etc/shadow` | Stores password hashes and password policies |
| `/etc/group` | Stores group information |
| `/etc/skel/` | Contains default files for new home directories |

## Learning Outcome
Learned how to create, modify, switch, and delete Linux user accounts.