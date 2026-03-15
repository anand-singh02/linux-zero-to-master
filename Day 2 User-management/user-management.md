# Linux User Management 👤

## Introduction

User management in Linux allows system administrators to create, modify, and manage user accounts on a system. Proper user management ensures security, access control, and system organization.

Linux supports multiple users, and each user has their own home directory, permissions, and environment.

---

# Important User Management Commands

## 1. whoami

Displays the username of the currently logged-in user.

Example:

```bash
whoami
```

Output example:

```bash
anand
```

---

## 2. id

Displays user ID (UID), group ID (GID), and groups associated with the current user.

Example:

```bash
id
```

Example output:

```bash
uid=1000(anand) gid=1000(anand) groups=1000(anand)
```

---

## 3. adduser

Used to create a new user account in Linux.

Example:

```bash
sudo adduser devopsuser
```

This command will:

* Create a new user
* Create a home directory
* Set up user password
* Create default configuration files

---

## 4. useradd

Another command used to create users with more manual control.

Example:

```bash
sudo useradd testuser
```

To create a home directory with user:

```bash
sudo useradd -m testuser
```

```bash
sudo useradd -g <group_name> -s /bin/bash -c "description" m -d /home/<user_name> <user_name>
```

---

## 5. passwd

Used to set or change the password of a user.

Example:

```bash
sudo passwd testuser
```

The system will prompt you to enter a new password.

---

## 6. userdel

Used to delete a user account.

Example:

```bash
sudo userdel testuser
```

To delete user along with their home directory:

```bash
sudo userdel -r testuser
```
Force delete even if the user is logged in:

```bash
sudo userdel -f testuser
```

---

## 7. groupadd

Creates a new group in Linux.

Example:

```bash
sudo groupadd developers
```

Groups help manage permissions for multiple users.

---

## 8. usermod

Used to modify an existing user account.

Example: To add user to a new group, but default group will remain same

```bash
sudo usermod -aG developers testuser
```

Here:

* `-a` means append
* `-G` specifies the group

Example: To change the default group

```bash
sudo usermod -g developer testuser
```
Here:

* `-g` change the group

Other usermod options:

* `-m -d /home/newfolder` To move the content of home folder to this new folder
* `-p` We can use passwd command also
* `-s` shell type
* `-L -U` Lock/Unlock a user no one can access it without unlocking

---

## 9. groups

Displays the groups a user belongs to.

Example:

```bash
groups
```

Example output:

```bash
anand sudo docker
```

---

## 10. su

Switch to another user account.

Example:

```bash
su username
```

Example:

```bash
su root
```

You will be asked to enter the password for that user.

---

## 11. sudo

Allows a permitted user to run commands with administrative privileges.

Example:

```bash
sudo apt update
```

Only users in the **sudo group** can use this command.

---

# Important Files Related to User Management

### /etc/passwd

Stores basic user account information.

Example entry:

```bash
anand:x:1000:1000:Anand Singh:/home/anand:/bin/bash
```

---

### /etc/shadow

Stores encrypted user passwords.

This file is accessible only by the root user.

---

### /etc/group

Stores group information.

Example entry:

```bash
developers:x:1001:testuser
```

---

# Summary

Linux user management is essential for controlling access to system resources. Commands like `adduser`, `userdel`, `passwd`, and `usermod` help administrators manage users efficiently while maintaining system security.

---

# Author

Anand Singh
B.Tech Graduate | Learning Linux for Cloud and DevOps
