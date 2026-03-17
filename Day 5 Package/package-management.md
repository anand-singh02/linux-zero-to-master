# 📅 Day 5 - Linux Package Management

Today I learned about **Package Management in Linux**. Package management helps users install, update, remove, and manage software easily using package managers.

---

## 📦 What is Package Management?

Package management is a system used in Linux to install, update, configure, and remove software packages.

Instead of downloading software manually, Linux uses **package managers** to automate the process.

---

## 🔧 Popular Package Managers

| Distribution | Package Manager |
|---------------|----------------|
| Ubuntu / Debian | APT |
| RedHat / CentOS | YUM / DNF |
| Arch Linux | Pacman |

---

What is the difference between

 Update & Upgrade?

Upgrade: Will delete the old packages
Update: Keep the old packages, we can rollback

# 🐧 APT Package Management (Debian/Ubuntu)

APT (Advanced Package Tool) is used in Debian-based systems like **Ubuntu**.

---

## 🔄 Update Package List

Update the list of available packages from repositories.

```bash
sudo apt update
```

⬆️ Upgrade Installed Packages

Upgrade all installed packages to the latest version.
```bash
sudo apt upgrade
```
📥 Install a Package

Install a new package.

```bash
sudo apt install <package_name>
```

Example:
```bash
sudo apt install nginx
```

❌ Remove a Package

Remove an installed package.
```bash
sudo apt remove <package_name>
```

Example:
```bash
sudo apt remove nginx
```

🧹 Remove Unused Packages

Remove unnecessary dependencies.

```bash
sudo apt autoremove
```

🔍 Search for a Package

Search for packages in the repository.

```bash
apt search <package_name>
```
Example:
```bash
apt search docker
```

ℹ️ Show Package Information

Display detailed information about a package.

```bash
apt show <package_name>
```

Example:
```bash
apt show nginx
```

📂 List Installed Packages
```bash
apt list --installed
```
📦 YUM / DNF Package Management (RedHat Based)

Used in CentOS, RHEL, Fedora.

Install Package
```bash
sudo yum install <package_name>
```
or
```bash
sudo dnf install <package_name>
```
Update Packages

```bash
sudo yum update
```
or
```bash
sudo dnf update
```
Check available Update 
```bash
sudo yum check-update
```

Remove Package
```bash
sudo yum remove <package_name>
```

To see the past work done related to packages, which will show you the activity with date and time

```bash
sudo yum history
```

We can simply undo or redo any action using

```bash
sudo yum history undo/redo <id>
```

From Redhat/Centos 8

```bash
 sudo dnf list available

 sudo dnf list installe

 sudo dnf update/upgrade
 sudo dnf install package.name

 sudo dnf remove package.name

 sudo dnf info package.name

 sudo dnf search package
```

📦 Pacman (Arch Linux)
Install Package
```bash
sudo pacman -S <package_name>
```
Update System
```bash
sudo pacman -Syu
```
Remove Package
```bash
sudo pacman -R <package_name>
```
🎯 Key Takeaways

Linux uses package managers to handle software installation.

APT is used in Debian-based systems.

YUM / DNF are used in RedHat-based systems.

Pacman is used in Arch Linux.

Package managers automatically handle dependencies.
