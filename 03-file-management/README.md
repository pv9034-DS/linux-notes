# File Management Commands

## Introduction

File management is one of the most important Linux skills. These commands help create, copy, move, delete, search, and manipulate files and directories.

---

## Copy Files and Directories

### cp

Copy a file.

```bash
cp source.txt destination.txt
```

Example:

```bash
cp notes.txt backup.txt
```

### Copy a Directory

```bash
cp -r project backup_project
```

`-r` means recursive copy.

---

## Move and Rename Files

### mv

Move a file to another directory.

```bash
mv file.txt Documents/
```

Rename a file.

```bash
mv oldname.txt newname.txt
```

Rename a directory.

```bash
mv old_folder new_folder
```

---

## Remove Files

### rm

Delete a file.

```bash
rm file.txt
```

Delete multiple files.

```bash
rm file1.txt file2.txt
```

Force delete without confirmation.

```bash
rm -f file.txt
```

---

## Remove Directories

### rmdir

Remove an empty directory.

```bash
rmdir test
```

### Remove Directory and Contents

```bash
rm -r project
```

Force remove.

```bash
rm -rf project
```

⚠️ Be careful with `rm -rf`. Deleted files usually cannot be recovered.

---

## Find Files and Directories

### find

Search for files.

```bash
find . -name file.txt
```

Search for directories.

```bash
find . -type d -name project
```

Search all Python files.

```bash
find . -name "*.py"
```

---

## Count Words, Lines, and Characters

### wc

Count lines, words, and characters.

```bash
wc file.txt
```

Count only lines.

```bash
wc -l file.txt
```

Count only words.

```bash
wc -w file.txt
```

Count only characters.

```bash
wc -c file.txt
```

---

## Extract Columns

### cut

Extract specific fields from text.

Example:

```text
John,25,Developer
```

Command:

```bash
cut -d "," -f1 file.txt
```

Output:

```text
John
```

Extract multiple fields.

```bash
cut -d "," -f1,3 file.txt
```

---

## Write Output to File and Terminal

### tee

Display output and save it to a file.

```bash
echo "Hello Linux" | tee output.txt
```

Append output.

```bash
echo "New Line" | tee -a output.txt
```

Useful for logging command output.

---

## Create Links

### Hard Link

```bash
ln original.txt hardlink.txt
```

A hard link points directly to the file's data.

---

### Symbolic Link

```bash
ln -s original.txt symlink.txt
```

A symbolic link acts like a shortcut.

View symbolic links:

```bash
ls -l
```

Example Output:

```text
symlink.txt -> original.txt
```

---

## File Comparison

### diff

Compare two files.

```bash
diff file1.txt file2.txt
```

Shows differences line by line.

---

## Sort File Content

### sort

Sort text alphabetically.

```bash
sort names.txt
```

Sort numbers.

```bash
sort -n numbers.txt
```

---

## Summary

Commands covered:

* cp
* mv
* rm
* rmdir
* find
* wc
* cut
* tee
* ln
* diff
* sort

These commands are essential for managing files and directories in Linux systems.
