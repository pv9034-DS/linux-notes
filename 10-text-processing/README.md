# Text Processing Commands

## Introduction

Text processing is one of the most powerful features of Linux. These commands help search, filter, modify, sort, and analyze text data efficiently.

They are heavily used in:

- DevOps
- System Administration
- Log Analysis
- Data Processing
- Shell Scripting

---

## grep

Search for text patterns in files.

### Search for a Word

```bash
grep "error" logfile.txt
```

---

### Ignore Case

```bash
grep -i "error" logfile.txt
```

---

### Show Line Numbers

```bash
grep -n "error" logfile.txt
```

---

### Recursive Search

```bash
grep -r "error" .
```

---

### Count Matches

```bash
grep -c "error" logfile.txt
```

---

## sort

Sort lines alphabetically.

```bash
sort names.txt
```

---

### Sort Numbers

```bash
sort -n numbers.txt
```

---

### Reverse Order

```bash
sort -r names.txt
```

---

## uniq

Remove duplicate lines.

```bash
uniq data.txt
```

---

### Count Duplicates

```bash
uniq -c data.txt
```

---

### Show Only Duplicate Lines

```bash
uniq -d data.txt
```

---

## cut

Extract specific columns.

Example file:

```text
John,25,Developer
Piyush,21,Student
```

---

Extract first column:

```bash
cut -d "," -f1 file.txt
```

Output:

```text
John
Piyush
```

---

Extract multiple columns:

```bash
cut -d "," -f1,3 file.txt
```

---

## tr

Translate or replace characters.

Convert lowercase to uppercase:

```bash
echo "linux" | tr 'a-z' 'A-Z'
```

Output:

```text
LINUX
```

---

Replace spaces:

```bash
echo "hello world" | tr ' ' '-'
```

Output:

```text
hello-world
```

---

## awk

A powerful text processing language.

Example file:

```text
John 50000
Piyush 60000
Rahul 45000
```

---

Print first column:

```bash
awk '{print $1}' file.txt
```

---

Print second column:

```bash
awk '{print $2}' file.txt
```

---

Print multiple columns:

```bash
awk '{print $1, $2}' file.txt
```

---

Filter records:

```bash
awk '$2 > 50000' file.txt
```

---

Calculate total:

```bash
awk '{sum += $2} END {print sum}' file.txt
```

---

## sed

Stream editor used for searching and replacing text.

Replace first occurrence:

```bash
sed 's/linux/Linux/' file.txt
```

---

Replace all occurrences:

```bash
sed 's/linux/Linux/g' file.txt
```

---

Edit file directly:

```bash
sed -i 's/linux/Linux/g' file.txt
```

---

Delete a line:

```bash
sed '3d' file.txt
```

---

Print a specific line:

```bash
sed -n '5p' file.txt
```

---

## xargs

Convert standard input into command arguments.

Example:

```bash
cat files.txt | xargs rm
```

---

Create directories:

```bash
echo "dir1 dir2 dir3" | xargs mkdir
```

---

## Combining Commands

Search and count errors:

```bash
grep "error" logfile.txt | wc -l
```

---

Find unique values:

```bash
sort data.txt | uniq
```

---

Display second column:

```bash
cat file.txt | awk '{print $2}'
```

---

Replace text and save:

```bash
sed 's/old/new/g' file.txt > updated.txt
```

---

## Summary

Commands covered:

- grep
- sort
- uniq
- cut
- tr
- awk
- sed
- xargs

These tools are essential for Linux automation, shell scripting, log analysis, DevOps workflows, and system administration.
