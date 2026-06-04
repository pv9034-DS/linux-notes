# Storage Management and LVM

## Introduction

Linux provides powerful tools for managing disks, partitions, file systems, and storage volumes.

LVM (Logical Volume Manager) offers flexible storage management by allowing volumes to be resized without repartitioning disks.

This topic is important for:

- Linux Administration
- DevOps
- Cloud Computing
- AWS EC2
- Server Management

---

## View Storage Devices

### lsblk

List all block storage devices.

```bash
lsblk
```

Example Output:

```text
sda      8:0    0   50G
├─sda1   8:1    0    1G
└─sda2   8:2    0   49G
```

---

### fdisk

Display partition information.

```bash
sudo fdisk -l
```

List all disks and partitions.

---

## File Systems

Display mounted file systems:

```bash
df -h
```

Display file system type:

```bash
df -Th
```

---

## Mounting File Systems

### mount

Mount a partition.

```bash
sudo mount /dev/sdb1 /mnt
```

Verify:

```bash
df -h
```

---

### umount

Unmount a partition.

```bash
sudo umount /mnt
```

or

```bash
sudo umount /dev/sdb1
```

---

## LVM Overview

LVM consists of three layers:

```text
Physical Volume (PV)
        ↓
Volume Group (VG)
        ↓
Logical Volume (LV)
```

Benefits:

- Easy resizing
- Flexible storage allocation
- Better disk management
- Snapshots support

---

## Physical Volumes

### Create Physical Volume

```bash
sudo pvcreate /dev/sdb
```

View physical volumes:

```bash
sudo pvs
```

Detailed information:

```bash
sudo pvdisplay
```

---

## Volume Groups

### Create Volume Group

```bash
sudo vgcreate data_vg /dev/sdb
```

View volume groups:

```bash
sudo vgs
```

Detailed information:

```bash
sudo vgdisplay
```

---

## Logical Volumes

### Create Logical Volume

```bash
sudo lvcreate -L 5G -n data_lv data_vg
```

Where:

- L = Size
- n = Name

Example:

```bash
sudo lvcreate -L 10G -n backup_lv data_vg
```

---

### View Logical Volumes

```bash
sudo lvs
```

Detailed view:

```bash
sudo lvdisplay
```

---

## Create File System

Format logical volume:

```bash
sudo mkfs.ext4 /dev/data_vg/data_lv
```

---

## Mount Logical Volume

Create mount point:

```bash
sudo mkdir /data
```

Mount volume:

```bash
sudo mount /dev/data_vg/data_lv /data
```

Verify:

```bash
df -h
```

---

## Extend Logical Volume

Increase volume size:

```bash
sudo lvextend -L +5G /dev/data_vg/data_lv
```

Or use all free space:

```bash
sudo lvextend -l +100%FREE /dev/data_vg/data_lv
```

---

## Resize File System

For ext4:

```bash
sudo resize2fs /dev/data_vg/data_lv
```

Verify:

```bash
df -h
```

---

## Reduce Logical Volume

⚠️ Always backup data before reducing volumes.

Unmount volume:

```bash
sudo umount /data
```

Check file system:

```bash
sudo e2fsck -f /dev/data_vg/data_lv
```

Resize file system:

```bash
sudo resize2fs /dev/data_vg/data_lv 5G
```

Reduce logical volume:

```bash
sudo lvreduce -L 5G /dev/data_vg/data_lv
```

---

## Remove LVM Components

Remove logical volume:

```bash
sudo lvremove /dev/data_vg/data_lv
```

Remove volume group:

```bash
sudo vgremove data_vg
```

Remove physical volume:

```bash
sudo pvremove /dev/sdb
```

---

## Useful Commands

Display block devices:

```bash
lsblk
```

Display file systems:

```bash
df -h
```

Display physical volumes:

```bash
pvs
```

Display volume groups:

```bash
vgs
```

Display logical volumes:

```bash
lvs
```

---

## Summary

Commands covered:

- lsblk
- fdisk
- mount
- umount
- pvcreate
- pvs
- pvdisplay
- vgcreate
- vgs
- vgdisplay
- lvcreate
- lvs
- lvdisplay
- lvextend
- resize2fs
- lvremove
- vgremove
- pvremove

Key concepts:

- Physical Volume (PV)
- Volume Group (VG)
- Logical Volume (LV)
- Mounting
- File Systems
- Storage Expansion

LVM is widely used in enterprise Linux environments because it provides flexible and scalable storage management.
