# Permissions and Ownership

## Introduction

Linux uses permissions and ownership to control who can access files and directories. Understanding permissions is essential for system administration, DevOps, cloud computing, and security.

---

## File Permissions

Run:

```bash
ls -l
```

Example Output:

```text
-rw-r--r-- 1 piyush users 1200 Jun 4 10:00 notes.txt
```

Permission Breakdown:

```text
-rw-r--r--
```

| Symbol | Meaning |
|----------|----------|
| - | File |
| d | Directory |
| r | Read |
| w | Write |
| x | Execute |

---

## Permission Groups

Permissions are divided into three groups:

```text
Owner | Group | Others
```

Example:

```text
rw- r-- r--
```

Meaning:

- Owner → Read + Write
- Group → Read
- Others → Read

---

## chmod

Used to change file permissions.

### Symbolic Method

Add execute permission:

```bash
chmod +x script.sh
```

Remove write permission:

```bash
chmod -w file.txt
```

Add read permission to group:

```bash
chmod g+r file.txt
```

---

### Numeric Method

| Number | Permission |
|----------|----------|
| 4 | Read |
| 2 | Write |
| 1 | Execute |

Examples:

```text
7 = rwx
6 = rw-
5 = r-x
4 = r--
```

---

### Common chmod Examples

Full permissions:

```bash
chmod 777 file.txt
```

Owner full access:

```bash
chmod 755 script.sh
```

Owner read/write only:

```bash
chmod 600 secret.txt
```

Typical website permissions:

```bash
chmod 644 index.html
```

---

## chown

Change file ownership.

Syntax:

```bash
sudo chown user file.txt
```

Example:

```bash
sudo chown piyush notes.txt
```

Change owner and group:

```bash
sudo chown piyush:developers notes.txt
```

---

## chgrp

Change group ownership.

Syntax:

```bash
sudo chgrp developers notes.txt
```

Verify:

```bash
ls -l
```

---

## umask

Sets default permissions for newly created files and directories.

Check current umask:

```bash
umask
```

Example Output:

```text
0022
```

---

### Common umask Values

| Umask | File Permission | Directory Permission |
|---------|---------|---------|
| 022 | 644 | 755 |
| 002 | 664 | 775 |
| 077 | 600 | 700 |

---

## Recursive Permission Changes

Change permissions for all files and folders:

```bash
chmod -R 755 project/
```

Change ownership recursively:

```bash
sudo chown -R piyush:developers project/
```

---

## Special Permissions

### SUID

Allows a file to run with the owner's privileges.

```bash
chmod u+s file
```

---

### SGID

Allows files created in a directory to inherit the group's ownership.

```bash
chmod g+s directory
```

---

### Sticky Bit

Commonly used on shared directories like /tmp.

```bash
chmod +t directory
```

---

## Verify Permissions

Display permissions:

```bash
ls -l
```

Display numeric permissions:

```bash
stat file.txt
```

---

## Summary

Commands covered:

- chmod
- chown
- chgrp
- umask
- stat

Important concepts:

- Read, Write, Execute
- Owner, Group, Others
- Numeric Permissions
- Recursive Permissions
- Special Permissions (SUID, SGID, Sticky Bit)

Permissions are one of the most important Linux topics for system administration, DevOps, AWS, and security.
