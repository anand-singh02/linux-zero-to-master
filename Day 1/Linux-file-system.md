# Day 1 – Linux File System 📂

## Introduction

The Linux file system is the way Linux organizes and stores files and directories on a system. Everything in Linux is treated as a file, including hardware devices, configuration files, and system processes.

The Linux file system follows a **hierarchical structure**, which means it is organized like a tree with a single top directory called the **root directory**.

---
## Some Linux Commands

* `lsblk -m` 
* `df -Th` To see the partion in the filesystem, type, size, used, available, mount with of the file system.
* `cat /etc/fstab` 
---
Q: What is inode ?
An inode in Linux is a data structure that stores metadata about a file or directory.

The filesystem uses the inode number to locate the inode, which then contains pointers to the data blocks where the actual file data is stored.
To see inode number use `ls -li`

---
## Root Directory (/)

The root directory is represented by a **forward slash `/`**.

It is the top-most directory in Linux, and all other directories and files exist under it.

Example:
<img src="./images/Linux-filesystem-structure.png01" alt="Alt text" width="500"/>

---

## Important Linux Directories

### /bin

Contains essential binary (executable) commands used by all users.

Examples:

* `ls`
* `cp`
* `mv`
* `cat`

---
### /etc

The `/etc` directory contains **system-wide configuration files** used by the Linux operating system and installed applications.

It stores important settings that control how the system behaves, including user accounts, network configuration, services, and system startup settings.

System administrators modify files in this directory to configure system behavior.

Examples of important files:

```bash
/etc/passwd
/etc/shadow
/etc/hosts
/etc/hostname
/etc/fstab
```

For example, `/etc/hosts` maps hostnames to IP addresses.

---
### /boot

Contains files required for booting the Linux system.

Examples include:

* Kernel files
* Bootloader files

---

### /dev

Contains device files that represent hardware devices.

Examples:

* Hard drives
* USB devices
* System devices

---

### /etc

Contains system configuration files.

Examples:

* Network configuration
* User account settings
* System service configuration

---

### /home

Contains personal directories for each user.

Example:

```
/home/anand
```

This directory stores user files like documents, downloads, and projects.

---

### /lib

Contains shared libraries needed by system programs and commands.

These libraries help programs run correctly.

---

### /tmp

Used to store temporary files created by applications or the system.

Files in this directory are usually deleted after system reboot.

---

### /usr

Contains user-installed programs, utilities, and libraries.

Common subdirectories include:

* `/usr/bin`
* `/usr/lib`
* `/usr/share`

---

### /var

Contains variable data files that change frequently.

Examples include:

* Log files
* Mail files
* Cache files

---

## Key Concept: Everything is a File

In Linux, everything is treated as a file. This includes:

* Regular files
* Directories
* Hardware devices
* System processes

This design makes Linux powerful and flexible.

---

## Useful Commands to Explore the File System

### Show current directory

```bash
pwd
```

---

### List files and directories

```bash
ls
```

---

### List files with details

```bash
ls -l
```

---

### Show hidden files

```bash
ls -a
```

---

## Summary

The Linux file system organizes data in a hierarchical structure starting from the root directory `/`. Understanding the file system is essential for navigating, managing files, and working efficiently in Linux.

---

## Author

Anand Singh
B.Tech Graduate | Learning Linux for Cloud and DevOps
