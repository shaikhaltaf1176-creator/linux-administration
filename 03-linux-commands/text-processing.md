# Linux Text Processing Commands

## Overview
Text-processing commands help Linux administrators search, filter, sort, and manipulate text from files and command output.

## Commands

| Command | Description |
|---|---|
| `grep` | Searches for specific text |
| `find` | Searches for files and directories |
| `sort` | Sorts lines of text |
| `uniq` | Removes adjacent duplicate lines |
| `cut` | Extracts selected columns |
| `awk` | Processes structured text |
| `sed` | Searches and modifies text |
| `wc` | Counts lines, words, and characters |
| `tr` | Translates or deletes characters |
| `diff` | Compares two files |

## Practical Examples

```bash
# Create sample file
cat > names.txt <<EOF
Altaf
Rahul
Amit
Rahul
Zoya
EOF

# Search for a word
grep "Rahul" names.txt

# Sort the content
sort names.txt

# Remove adjacent duplicate lines
sort names.txt | uniq

# Count lines, words and characters
wc names.txt

# Display the first column
cut -d " " -f 1 names.txt

# Convert lowercase to uppercase
cat names.txt | tr 'a-z' 'A-Z'

# Find a file
find . -name "names.txt"

# Compare two files
diff names.txt backup.txt

# Display matching lines with line numbers
grep -n "Rahul" names.txt
```

## Understanding Pipes and Redirection

### Pipe (|)
Passes the output of one command as input to another command.

```bash
ls -l | grep ".txt"
```

### Output Redirection (>)

Saves command output into a file and overwrites existing content.

```bash
ls > files.txt
```

### Append (>>)

Adds command output to the end of a file.

```bash
date >> files.txt
```

## Learning Outcome
Learned how to search, filter, sort, compare, and manipulate text using Linux commands.