# Linux Directory Structure

Linux uses a hierarchical directory structure that starts from the root directory (`/`). All files and directories are organized under this root directory.

## Important Linux Directories

| Directory | Description |
|---|---|
| `/` | Root directory; starting point of the filesystem |
| `/home` | Stores personal directories of users |
| `/root` | Home directory of the root user |
| `/etc` | Contains system configuration files |
| `/var` | Stores logs and frequently changing data |
| `/tmp` | Stores temporary files |
| `/bin` | Contains essential user commands |
| `/sbin` | Contains system administration commands |
| `/boot` | Contains bootloader and kernel files |
| `/dev` | Contains device files |
| `/proc` | Provides information about running processes and the kernel |
| `/opt` | Stores optional application software |
| `/mnt` | Used for temporary filesystem mounting |
| `/media` | Mount point for removable devices |
| `/usr` | Contains user applications, utilities and libraries |

## Useful Commands

```bash
# Display current directory
pwd

# List files and directories
ls

# Show hidden files
ls -la

# Display directory structure
tree /

# Change directory
cd /etc

# Go to home directory
cd ~

# Go to root directory
cd /
```

## Practical Example

```bash
cd /home
mkdir linux-practice
cd linux-practice
pwd
```

**Expected output:**
```text
/home/linux-practice
```

## Key Points
- Linux follows a hierarchical filesystem.
- The root directory `/` is the starting point.
- Every file and directory belongs somewhere under `/`.
- Linux is case-sensitive.