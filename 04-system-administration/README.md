# System Administration

## Introduction

System administration involves managing users, groups, system information, and administrative tasks in Linux. These commands are commonly used by Linux administrators, DevOps engineers, and cloud engineers.

---

## System Information

### uname

Display system information.

```bash
uname
```

Display detailed system information.

```bash
uname -a
```

Example Output:

```text
Linux ubuntu 6.8.0 x86_64 GNU/Linux
```

---

### hostname

Display the system hostname.

```bash
hostname
```

Set a new hostname temporarily.

```bash
sudo hostname new-hostname
```

---

### uptime

Display how long the system has been running.

```bash
uptime
```

Example Output:

```text
10:15:20 up 2 days, 5:32, 2 users, load average: 0.15, 0.10, 0.08
```

---

## User Information

### whoami

Display the current logged-in user.

```bash
whoami
```

Example Output:

```text
piyush
```

---

### who

Display all logged-in users.

```bash
who
```

---

### id

Display user ID and group information.

```bash
id
```

Example Output:

```text
uid=1000(piyush) gid=1000(piyush)
```

---

### which

Locate the executable path of a command.

```bash
which python
```

Example Output:

```text
/usr/bin/python
```

---

## Administrative Commands

### sudo

Run commands with administrative privileges.

```bash
sudo apt update
```

The system may ask for your password.

---

### su

Switch to another user.

```bash
su username
```

Switch to root user.

```bash
su -
```

---

## User Management

### useradd

Create a new user.

```bash
sudo useradd john
```

Create a user with a home directory.

```bash
sudo useradd -m john
```

---

### passwd

Set or change a user's password.

```bash
sudo passwd john
```

Change your own password.

```bash
passwd
```

---

### userdel

Delete a user.

```bash
sudo userdel john
```

Delete user and home directory.

```bash
sudo userdel -r john
```

---

## Group Management

### groupadd

Create a new group.

```bash
sudo groupadd developers
```

---

### groupdel

Delete a group.

```bash
sudo groupdel developers
```

---

### groups

Display groups a user belongs to.

```bash
groups
```

---

### usermod

Add a user to a group.

```bash
sudo usermod -aG developers john
```

Verify:

```bash
groups john
```

---

## Process Monitoring

### ps

Display running processes.

```bash
ps
```

Display all processes.

```bash
ps aux
```

---

### top

Display real-time system processes.

```bash
top
```

Exit by pressing:

```text
q
```

---

### kill

Terminate a process using PID.

```bash
kill 1234
```

Force terminate.

```bash
kill -9 1234
```

---

## Summary

Commands covered:

- uname
- hostname
- uptime
- whoami
- who
- id
- which
- sudo
- su
- useradd
- passwd
- userdel
- groupadd
- groupdel
- usermod
- groups
- ps
- top
- kill

These commands are essential for managing Linux systems, users, groups, and processes.
