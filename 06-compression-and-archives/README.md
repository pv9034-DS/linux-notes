# Compression and Archives

## Introduction

Compression reduces file size, while archiving combines multiple files into a single file. Linux provides several tools for compressing and archiving data.

---

## zip

Create a compressed ZIP archive.

### Compress a File

```bash
zip archive.zip file.txt
```

### Compress Multiple Files

```bash
zip archive.zip file1.txt file2.txt file3.txt
```

### Compress a Directory

```bash
zip -r project.zip project/
```

`-r` means recursive.

---

## unzip

Extract ZIP archives.

### Extract Archive

```bash
unzip archive.zip
```

### Extract to Specific Directory

```bash
unzip archive.zip -d extracted/
```

### View Archive Contents

```bash
unzip -l archive.zip
```

---

## gzip

Compress files using GNU Zip.

### Compress a File

```bash
gzip file.txt
```

After compression:

```text
file.txt.gz
```

---

### Keep Original File

```bash
gzip -k file.txt
```

---

## gunzip

Decompress gzip files.

```bash
gunzip file.txt.gz
```

Equivalent command:

```bash
gzip -d file.txt.gz
```

---

## tar

Used for archiving files and directories.

### Create Archive

```bash
tar -cvf archive.tar project/
```

Options:

- c → Create archive
- v → Verbose output
- f → File name

---

### View Archive Contents

```bash
tar -tvf archive.tar
```

---

### Extract Archive

```bash
tar -xvf archive.tar
```

Options:

- x → Extract
- v → Verbose
- f → Archive file

---

## Create Compressed Tar Archive

### tar + gzip

```bash
tar -czvf backup.tar.gz project/
```

Options:

- c → Create
- z → gzip compression
- v → Verbose
- f → File

---

### Extract tar.gz Archive

```bash
tar -xzvf backup.tar.gz
```

---

## Create tar.bz2 Archive

```bash
tar -cjvf backup.tar.bz2 project/
```

Extract:

```bash
tar -xjvf backup.tar.bz2
```

---

## Create tar.xz Archive

```bash
tar -cJvf backup.tar.xz project/
```

Extract:

```bash
tar -xJvf backup.tar.xz
```

---

## Compare Compression Methods

| Tool | Compression | Common Use |
|--------|--------|--------|
| zip | Medium | Cross-platform sharing |
| gzip | Good | Linux log files |
| tar | None | Archiving only |
| tar.gz | Good | Linux backups |
| tar.bz2 | Better | Larger archives |
| tar.xz | Best | Maximum compression |

---

## Backup Example

Create backup:

```bash
tar -czvf backup.tar.gz Documents/
```

Restore backup:

```bash
tar -xzvf backup.tar.gz
```

---

## Summary

Commands covered:

- zip
- unzip
- gzip
- gunzip
- tar

Common archive formats:

- .zip
- .gz
- .tar
- .tar.gz
- .tar.bz2
- .tar.xz

These tools are widely used for backups, file transfers, and system administration tasks.
