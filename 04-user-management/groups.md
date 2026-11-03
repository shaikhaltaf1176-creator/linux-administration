# Linux Group Management

## Overview
Linux groups help administrators manage permissions for multiple users together. Instead of assigning permissions individually, users can be added to groups and share access to resources.

## Group Management Commands

| Command | Description |
|---|---|
| `groups` | Displays groups of the current user |
| `id` | Displays user and group IDs |
| `groupadd` | Creates a new group |
| `groupmod` | Modifies a group |
| `groupdel` | Deletes a group |
| `usermod -aG` | Adds a user to a supplementary group |
| `gpasswd -d` | Removes a user from a group |
| `getent group` | Displays group information |

## Practical Examples

### 1. Create a group

```bash
sudo groupadd developers
```

### 2. Create a user

```bash
sudo useradd -m altaf
```

### 3. Add a user to a group

```bash
sudo usermod -aG developers altaf
```

### 4. Check user groups

```bash
groups altaf
```

### 5. Display group information

```bash
getent group developers
```

### 6. Remove a user from a group

```bash
sudo gpasswd -d altaf developers
```

### 7. Modify a group name

```bash
sudo groupmod -n programmers developers
```

### 8. Delete a group

```bash
sudo groupdel programmers
```

## Primary Group vs Supplementary Group

| Primary Group | Supplementary Group |
|---|---|
| Main group associated with a user | Additional groups assigned to a user |
| Usually assigned during user creation | Can be added later |
| One primary group per user | Multiple supplementary groups possible |

## Important File

`/etc/group` stores Linux group information.

## Learning Outcome
Learned how to create groups, add and remove users, and manage group membership.