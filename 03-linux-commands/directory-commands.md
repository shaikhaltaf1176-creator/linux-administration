# Linux Directory Management Commands

## Overview
Directories are used to organize files and maintain a structured filesystem. Linux provides commands to create, navigate, list, and remove directories.

## Commands

| Command | Description |
|---|---|
| `ls` | Lists files and directories |
| `ls -l` | Displays detailed listing |
| `ls -a` | Displays hidden files |
| `cd` | Changes directory |
| `cd ..` | Moves to the parent directory |
| `cd ~` | Moves to the home directory |
| `mkdir` | Creates a directory |
| `mkdir -p` | Creates nested directories |
| `rmdir` | Removes an empty directory |
| `rm -r` | Removes a directory and its contents |
| `tree` | Displays directory structure |

## Practical Examples

```bash
# List files and directories
ls

# Display detailed information
ls -l

# Show hidden files
ls -a

# Create a directory
mkdir projects

# Create nested directories
mkdir -p projects/linux/practice

# Navigate into a directory
cd projects

# Move to the parent directory
cd ..

# Go to home directory
cd ~

# Display directory structure
tree projects

# Remove an empty directory
rmdir projects

# Remove a directory and its contents
rm -r projects
```

## Important Notes
- `.` represents the current directory.
- `..` represents the parent directory.
- `~` represents the current user's home directory.
- Use `rm -r` carefully because it deletes directory contents.

## Learning Outcome
Learned how to create, navigate, organize, and remove directories in Linux.