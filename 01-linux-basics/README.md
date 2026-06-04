# Linux Basics

## What is Linux?

Linux is a free and open-source operating system kernel created by Linus Torvalds in 1991. It is widely used in servers, cloud computing, embedded systems, and software development environments.

### Why Learn Linux?

* Most cloud servers run Linux
* Essential for DevOps and System Administration
* Widely used in software development
* Open-source and highly customizable
* Strong security and stability

---

## Ways to Install Linux

### 1. WSL (Windows Subsystem for Linux)

WSL allows Linux to run directly on Windows without a virtual machine.

**Advantages:**

* Easy to install
* Good performance
* Suitable for development

### 2. Virtual Machine

Tools such as VirtualBox allow Linux to run inside another operating system.

**Advantages:**

* Safe testing environment
* No impact on the main operating system

### 3. Dual Boot

Linux and Windows are installed on the same computer.

**Advantages:**

* Full hardware performance
* Direct access to system resources

---

## Linux Architecture

Linux consists of several layers:

### Hardware

Physical components such as CPU, RAM, storage devices, and network interfaces.

### Kernel

The core of the operating system.

Responsibilities:

* Process management
* Memory management
* Device management
* File system management

### Shell

A command-line interface used to communicate with the kernel.

Examples:

* Bash
* Zsh
* Fish

### Applications

Programs used by end users such as browsers, editors, and development tools.

---

## Bootloader

A bootloader is a program that starts when the computer powers on and loads the operating system into memory.

Common Linux bootloader:

* GRUB (Grand Unified Bootloader)

---

## Common System Information Commands

### Check Running Processes

```bash
top
```

Displays active processes and system resource usage.

---

### Check Disk Usage

```bash
df -h
```

Shows disk space usage in a human-readable format.

---

### Check Memory Usage

```bash
free -h
```

Displays RAM and swap memory usage.

---

## Update Linux System

For Ubuntu:

```bash
sudo apt update
sudo apt upgrade
```

These commands refresh package information and install available updates.

---

## Summary

In this section, we learned:

* What Linux is
* Different installation methods
* Linux architecture
* Kernel and Shell concepts
* Bootloader basics
* Essential system monitoring commands
