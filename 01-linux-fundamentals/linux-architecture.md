# Linux Architecture

## What is Linux Architecture?

Linux architecture describes how different components of the Linux operating system work together to manage hardware, software, and user operations.

## Main Components

Linux architecture consists of five major components:

### 1. Hardware
Physical components of a computer:
- CPU
- RAM
- Hard Disk
- Network Interface Card

### 2. Kernel
The kernel is the core of Linux. It manages communication between hardware and software.

Responsibilities:
- Process management
- Memory management
- Device management
- File system management
- Network management

### 3. Shell
The shell acts as an interface between the user and the operating system.

Examples:
- Bash
- Zsh
- Sh

Example:
```bash
echo "Hello Linux"
```

### 4. System Utilities
These are tools used to perform system operations.

Examples:
- ls
- cp
- mv
- mkdir
- ps
- systemctl

### 5. Applications
Applications are programs that users run on Linux.

Examples:
- Web browsers
- Text editors
- Web servers
- Database applications

## Linux Architecture Flow

```text
        User
          |
     Applications
          |
     Shell / CLI
          |
   System Utilities
          |
        Kernel
          |
       Hardware
```

## Important Kernel Functions

| Function | Description |
|---|---|
| Process Management | Manages running processes |
| Memory Management | Allocates and manages RAM |
| Device Management | Controls hardware devices |
| File System Management | Handles files and directories |
| Network Management | Manages network communication |

## How to Check Kernel Information

```bash
uname -a
```

Check system information:

```bash
hostnamectl
```

## Conclusion

Linux architecture explains how users, applications, the shell, kernel, and hardware communicate. Understanding these components is essential for Linux system administration.