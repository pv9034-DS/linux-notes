# File System Commands

## Introduction

Linux stores everything in a hierarchical file system structure. Understanding basic navigation commands is essential for working efficiently in Linux.

---

## Present Working Directory

### pwd

Displays the current directory.

```bash
pwd
```

Example Output:

```text
/home/piyush/Documents
```

---

## List Files and Directories

### ls

Displays files and directories in the current location.

```bash
ls
```

### ls -l

Shows detailed information.

```bash
ls -l
```

### ls -la

Shows detailed information including hidden files.

```bash
ls -la
```

---

## Change Directory

### cd

Move into a directory.

```bash
cd Documents
```

### Move to Parent Directory

```bash
cd ..
```

### Move to Home Directory

```bash
cd
```

### Move to Previous Directory

```bash
cd -
```

---

## Create Directories

### mkdir

Create a new directory.

```bash
mkdir project
```

### Create Multiple Directories

```bash
mkdir dir1 dir2 dir3
```

### Create Nested Directories

```bash
mkdir -p project/src/components
```

---

## Create Files

### touch

Create an empty file.

```bash
touch notes.txt
```

Create multiple files.

```bash
touch file1.txt file2.txt file3.txt
```

---

## Display File Content

### cat

Display file contents.

```bash
cat notes.txt
```

### Display Multiple Files

```bash
cat file1.txt file2.txt
```

---

## View Beginning of File

### head

Display first 10 lines.

```bash
head file.txt
```

Display first 5 lines.

```bash
head -5 file.txt
```

---

## View End of File

### tail

Display last 10 lines.

```bash
tail file.txt
```

Display last 5 lines.

```bash
tail -5 file.txt
```

Monitor a log file in real time.

```bash
tail -f logfile.log
```

---

## Print Text

### echo

Display text on the terminal.

```bash
echo "Hello Linux"
```

Save text into a file.

```bash
echo "Hello Linux" > notes.txt
```

Append text to a file.

```bash
echo "Second line" >> notes.txt
```

---

## Clear Terminal Screen

### clear

```bash
clear
```

Shortcut:

```text
Ctrl + L
```

---

## Summary

Commands covered:

* pwd
* ls
* cd
* mkdir
* touch
* cat
* head
* tail
* echo
* clear

These commands form the foundation of Linux navigation and file system management.
