# Day 1 – Linux Introduction 🐧

Welcome to Day 1 of my Linux learning journey.

I have started learning Linux to build strong fundamentals for Cloud Computing and DevOps. This repository will document everything I learn step by step.

---

## What is Linux?

Linux is an open-source operating system based on the Unix architecture.  
It is widely used in servers, cloud platforms, and DevOps environments.

Most cloud providers like AWS, Azure, and GCP use Linux-based systems.

---

## Why I Am Learning Linux

- Build strong fundamentals for Cloud & DevOps
- Understand server environments
- Learn command line operations
- Automate tasks using shell scripting

---

## Linux Distributions

A Linux distribution (distro) is a version of Linux with additional software.

Examples:
- Ubuntu
- CentOS
- Red Hat
- Debian
- Kali Linux

---
# Linux Installation and Setup Guide 🐧

This guide explains how to set up a Linux environment in two common ways:

1. Running Linux on Windows using a virtual machine.
2. Running Linux on the cloud using AWS.

These methods are commonly used by developers, system administrators, and DevOps engineers to practice Linux.

---

# 1. Installing Linux on Windows Using VirtualBox

A virtual machine allows you to run Linux inside your Windows system without affecting your main operating system.

For this setup we use **Oracle VM VirtualBox**.

Here is the link of website:
https://www.virtualbox.org/
---

## Step 1: Download VirtualBox

Download and install **Oracle VM VirtualBox** from the official website.

After installation, open the VirtualBox application.

---

## Step 2: Download a Linux ISO File

Download a Linux distribution ISO file. A popular choice for beginners is **Ubuntu Linux**.

The ISO file is used to install the Linux operating system in the virtual machine.

Here is the link of website:
https://ubuntu.com/download/desktop

Download Long Term Support file 
---

## Step 3: Create a Virtual Machine

1. Open VirtualBox.
2. Click **New**.
3. Enter a name for the machine (Example: Ubuntu-Linux).
4. Select:

   * Type: Linux
   * Version: Ubuntu (64-bit)

Click **Next**.

---

## Step 4: Allocate Memory (RAM)

Assign memory to the virtual machine.

Recommended:

* Minimum: 2 GB
* Recommended: 4 GB

Click **Next**.

---

## Step 5: Create a Virtual Hard Disk

1. Select **Create a virtual hard disk now**.
2. Choose **VDI (VirtualBox Disk Image)**.
3. Select **Dynamically Allocated**.
4. Set disk size to **20 GB or more**.

Click **Create**.

---

## Step 6: Attach the Linux ISO File

1. Select the created virtual machine.
2. Click **Settings**.
3. Go to **Storage**.
4. Under **Controller IDE**, click **Empty**.
5. Select the downloaded Ubuntu ISO file.

---

## Step 7: Install Linux

1. Click **Start** to launch the virtual machine.
2. The Ubuntu installer will open.
3. Follow the installation steps:

   * Select language
   * Choose keyboard layout
   * Create username and password
   * Complete installation

After installation, restart the virtual machine and log in.

You now have a working Linux system running on Windows.

---

# 2. Setting Up Linux on AWS

AWS allows you to run Linux servers in the cloud using virtual machines called EC2 instances.

---

## Step 1: Login to AWS Console

Go to the AWS Management Console and login to your account.

---

## Step 2: Launch an EC2 Instance

1. Open **EC2 Dashboard**.
2. Click **Launch Instance**.
3. Choose a Linux image such as:

   * Ubuntu
   * Amazon Linux

---

## Step 3: Choose Instance Type

Select **t2.micro** or **t3.micro** (Free tier eligible).

Click **Next**.

---

## Step 4: Configure Security Group

Allow **SSH (Port 22)** so you can connect to the instance.

---

## Step 5: Create Key Pair

Create a **Key Pair** and download the `.pem` file.
This file will be used to securely connect to your Linux server.

---

## Step 6: Launch the Instance

Click **Launch Instance** and wait for the server to start.

---

## Step 7: Connect to the Linux Server

Use SSH to connect to your instance.

Example command:

```
ssh -i your-key.pem ubuntu@your-public-ip
```

After connecting, you will have access to a remote Linux server running on AWS.

---

# Author

Anand Singh
B.Tech Graduate | Aspiring Cloud & DevOps Engineer


## Basic Linux Concepts Learned Today

### 1. Terminal
The terminal is a command-line interface used to interact with the Linux system.

### 2. Root User
The root user has full administrative privileges in Linux.

### 3. Shell
The shell is a program that interprets commands entered in the terminal.

Example shells:
- bash
- sh
- zsh

---

## Basic Commands Practiced

### 1. `pwd`
Shows the current working directory.

Example:
```bash
pwd
