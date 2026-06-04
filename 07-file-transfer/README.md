# File Transfer Commands

## Introduction

File transfer is an essential Linux skill used for moving files between local systems, remote servers, and cloud instances. These commands are commonly used by system administrators, DevOps engineers, and cloud engineers.

---

## SCP (Secure Copy)

SCP is used to securely transfer files between systems over SSH.

### Copy a File to a Remote Server

```bash
scp file.txt user@server_ip:/home/user/
```

Example:

```bash
scp notes.txt ubuntu@192.168.1.10:/home/ubuntu/
```

---

### Copy a File from a Remote Server

```bash
scp user@server_ip:/home/user/file.txt .
```

Example:

```bash
scp ubuntu@192.168.1.10:/home/ubuntu/notes.txt .
```

---

### Copy an Entire Directory

```bash
scp -r project/ ubuntu@192.168.1.10:/home/ubuntu/
```

`-r` means recursive.

---

### Specify a Custom SSH Port

```bash
scp -P 2222 file.txt user@server_ip:/home/user/
```

---

## RSYNC

Rsync is used for efficient file synchronization and backups.

### Copy Files

```bash
rsync file.txt backup/
```

---

### Copy Directory

```bash
rsync -av project/ backup/
```

Options:

- a → Archive mode
- v → Verbose

---

### Sync to Remote Server

```bash
rsync -av project/ ubuntu@192.168.1.10:/home/ubuntu/
```

---

### Delete Removed Files

```bash
rsync -av --delete source/ destination/
```

---

### Show Progress

```bash
rsync -av --progress project/ backup/
```

---

## SFTP (SSH File Transfer Protocol)

Connect to a remote server.

```bash
sftp ubuntu@192.168.1.10
```

---

### Upload a File

```bash
put file.txt
```

---

### Download a File

```bash
get file.txt
```

---

### Upload a Directory

```bash
put -r project
```

---

### Exit SFTP

```bash
exit
```

---

## WGET

Download files from the internet.

### Download a File

```bash
wget https://example.com/file.zip
```

---

### Save with Different Name

```bash
wget -O backup.zip https://example.com/file.zip
```

---

### Continue Interrupted Download

```bash
wget -c https://example.com/file.zip
```

---

## CURL

Transfer data using URLs.

### Download a File

```bash
curl -O https://example.com/file.zip
```

---

### Save with Custom Name

```bash
curl -o backup.zip https://example.com/file.zip
```

---

### View Web Page Source

```bash
curl https://example.com
```

---

## AWS EC2 Examples

Copy a file to EC2:

```bash
scp -i my-key.pem app.py ubuntu@ec2-public-ip:/home/ubuntu/
```

Copy a directory to EC2:

```bash
scp -i my-key.pem -r project ubuntu@ec2-public-ip:/home/ubuntu/
```

Connect using SFTP:

```bash
sftp -i my-key.pem ubuntu@ec2-public-ip
```

---

## Comparison

| Command | Purpose |
|----------|----------|
| scp | Secure file copy |
| rsync | Synchronization and backup |
| sftp | Interactive file transfer |
| wget | Download files |
| curl | Transfer data using URLs |

---

## Summary

Commands covered:

- scp
- rsync
- sftp
- wget
- curl

These tools are widely used for file transfers, backups, server management, cloud computing, and DevOps workflows.
