# Linux Permission Management 🔐

## Introduction

Linux uses a permission system to control access to files and directories. Each file has an owner, a group, and permissions that determine who can read, write, or execute the file.

---

# Checking File Permissions

You can view permissions using:

```bash
ls -l
```

Example Output:

```
-rwxr-xr-- 1 anand devops 1024 Mar 16 script.sh
```

Permission Breakdown:

```
- rwx r-x r--
| │   │   │
| │   │   └── Others permissions
| │   └────── Group permissions
| └────────── Owner permissions
└────────── File type (file or directory)
```

---

# Permission Types

| Symbol | Meaning |
| ------ | ------- |
| r      | Read    |
| w      | Write   |
| x      | Execute |

---
# Ways To change permission of files 

* chmod u=rwx, g=rw, o=r file.txt
* chmod u+rwx file.txt
* chmod u-rw file.txt
* chmod 755 file.txt

---

# 1. chmod (Change File Permissions)

The `chmod` command modifies file permissions.

``` bash
chmod a+rwx file.txt
```
Here:
* `u` mean user
* `g` mean group
* `o` mean other
* `a` mean all

Example:

```bash
chmod 755 script.sh
```

Permission Meaning:

```
7 = rwx
5 = r-x
5 = r-x
```

Add execute permission:

```bash
chmod +x script.sh
```

Remove write permission:

```bash
chmod -w file.txt
```

---

# 2. chown (Change File Owner)

The `chown` command changes the owner of a file.

Example:

```bash
sudo chown user file.txt
```

Change owner and group:

```bash
sudo chown user:group file.txt
```

Example:

```bash
sudo chown anand:developers project.txt
```

---

# 3. chgrp (Change Group)

The `chgrp` command changes the group ownership of a file.

Example:

```bash
sudo chgrp developers file.txt
```

---

# Numeric Permission Table

| Number | Permission |
| ------ | ---------- |
| 7      | rwx        |
| 6      | rw-        |
| 5      | r-x        |
| 4      | r--        |
| 3      | -wx        |
| 2      | -w-        |
| 1      | --x        |
| 0      | ---        |

Example:

```bash
chmod 644 file.txt
```

Meaning:

Owner → read + write
Group → read
Others → read

---

# Summary

Linux permissions help secure files by controlling who can access them. Commands like `chmod`, `chown`, and `chgrp` allow administrators to manage file access and ownership effectively.

---

# Author

Anand Singh
B.Tech Graduate | Learning Linux for Cloud and DevOps
