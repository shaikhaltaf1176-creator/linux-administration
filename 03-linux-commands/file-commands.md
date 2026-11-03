# Linux File Management Commands

## Overview
Linux provides several commands to create, view, copy, move, rename, and delete files.

## Commands

| Command | Description |
|---|---|
| `touch` | Creates an empty file |
| `cat` | Displays file content |
| `less` | Views file content page by page |
| `head` | Displays the first 10 lines |
| `tail` | Displays the last 10 lines |
| `cp` | Copies files |
| `mv` | Moves or renames files |
| `rm` | Deletes files |
| `file` | Identifies file types |
| `wc` | Counts lines, words, and characters |
| `stat` | Displays file details |

## Practical Examples

```bash
# Create a file
touch file.txt

# Add content to a file
echo "Welcome to Linux" > file.txt

# Display file content
cat file.txt

# Copy a file
cp file.txt backup.txt

# Rename a file
mv file.txt linux.txt

# Display first 10 lines
head linux.txt

# Display last 10 lines
tail linux.txt

# Count lines, words and bytes
wc linux.txt

# Check file information
stat linux.txt

# Delete a file
rm backup.txt
```

## Important Notes
- `>` overwrites existing content.
- `>>` appends content without removing existing data.
- `rm` permanently removes files in normal command-line use. Check the filename before deleting.

## Learning Outcome
Learned how to create, read, copy, rename, move, and delete files in Linux.