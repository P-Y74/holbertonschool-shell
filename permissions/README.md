# Shell, Permissions ✨

<img src="https://github.com/user-attachments/assets/7d564981-cb81-43e7-819a-25ffcfc5bd72" width=40% height=40%>

## Overview

Welcome to **Shell, Permissions**! This repository contains a collection of scripts aimed at mastering file permissions, user management, and access control in a Unix-based system. The goal is to become proficient in managing file and directory permissions using command-line tools.

These scripts were created as part of a learning project aimed at solving various exercises on shell permissions. Each script addresses a specific requirement and helps to better understand user management and access rights in a Unix system.

## Table of Contents

1. [Resources](#resources-)
2. [Learning Objectives](#learning-objectives-)
3. [Project Requirements](#project-requirements-)
4. [Setup](#setup-)
5. [Scripts & Usage](#scripts--usage-)
   - [0. Change User](#0-change-user)
   - [1. Print Effective UID](#1-print-effective-uid)
   - [2. Groups](#2-groups)
   - [3. New Owner](#3-new-owner)
   - [4. Empty File](#4-empty-file)
   - [5. Execute Permission](#5-execute-permission)
   - [6. Multiple Permissions](#6-multiple-permissions)
   - [7. Everybody!](#7-everybody)
   - [8. James Bond](#8-james-bond)
   - [9. John Doe](#9-john-doe)
   - [10. Look in the Mirror](#10-look-in-the-mirror)
   - [11. Directories Permissions](#11-directories-permissions)
   - [12. Directory Permissions](#12-directory-permissions)
   - [13. Change Group](#13-change-group)
   - [14. Change Owner and Group](#14-change-owner-and-group)
   - [15. Symbolic Link Permissions](#15-symbolic-link-permissions)
   - [16. If Only](#16-if-only)
    
---

## Resources ✨

Here are some useful materials to help you understand shell permissions:

- **File Permissions in Linux**
- **User and Group Management**
- **Understanding chmod, chown, chgrp**
- **Special Permissions (SUID, SGID, Sticky Bit)**
- **Access Control Lists (ACLs)**

### Commands Covered:

```bash
chmod, sudo, su, chown, chgrp, id, groups, whoami, adduser, useradd, addgroup
```

---

## Learning Objectives 🎯

By the end of this project, you should be able to:

- Understand and manipulate file and directory permissions
- Use `chmod` to set permissions in symbolic and numeric mode
- Change file ownership with `chown`
- Modify group ownership using `chgrp`
- Utilize `sudo` and `su` for privilege escalation
- Understand special permissions like **SUID**, **SGID**, and **Sticky Bit**
- Work with **ACLs** to manage extended permissions
- Represent the three sets of permissions (owner, group, and other) as a single digit
- Explain why a normal user cannot use `chown` on a file
- Run commands with root privileges
- Change user ID or become a superuser
- Create users and groups
- Print real and effective user and group IDs
- Print the groups a user belongs to
- Print the effective user ID

---

## Project Requirements 👋

- Allowed editors: `vi`, `vim`, `emacs`
- Scripts must be exactly **two lines long** (`wc -l file` should print 2)
- The first line of each script must be `#!/bin/bash`
- Scripts must be executable (`chmod u+x filename.sh`)
- No use of **backticks**, `&&`, `||`, or `;`
- Tested on **Ubuntu 22.04 LTS`
- A `README.md` file at the root of the folder describing each script
- All files should end with a new line

---

## Setup ⚙️

To get started, clone this repository:

```bash
git clone https://github.com/yourusername/shell-permissions.git
```

Navigate to the directory and make the scripts executable:

```bash
chmod u+x script_name.sh
```

Run a script using:

```bash
./script_name.sh
```

---

## Scripts & Usage 🚀

### 0. Change User

Write a script that switches the current user to `betty`.
   * You should use exactly 8 characters for your command (+1 character for the new line)
   * You can assume that the user `betty` will exist when we will run your script

```bash
julien@ubuntu:/tmp/h$ tail -1 0-iam_betty | wc -c
9
julien@ubuntu:/tmp/h$
```

### 1. Print Effective UID

Write a script that prints the effective user ID of the current user.

```bash
julien@ubuntu:/tmp/h$ ./1-who_am_i
julien
julien@ubuntu:/tmp/h$
```

### 2. Groups

Write a script that prints all the groups the current user is part of.

```bash
julien@ubuntu:/tmp/h$ ./2-groups
julien adm cdrom sudo dip plugdev lpadmin sambashare
julien@ubuntu:/tmp/h$
```

### 3. New Owner

Write a script that changes the owner of the file `hello` to `betty`.

```bash
julien@ubuntu:/tmp$ ls -l
total 4
-rwxrw-r-- 1 julien julien 30 Sep 20 14:23 3-new_owner
-rw-rw-r-- 1 julien julien  0 Sep 20 14:18 hello
julien@ubuntu:/tmp$ sudo ./3-new_owner 
julien@ubuntu:/tmp$ ls -l
total 4
-rwxrw-r-- 1 julien julien 30 Sep 20 14:23 3-new_owner
-rw-rw-r-- 1 betty  julien  0 Sep 20 14:18 hello
julien@ubuntu:/tmp$
```

### 4. Empty File

Write a script that creates an empty file called `hello`.


### 5. Execute Permission

Write a script that adds execute permission to `hello` for the owner.
   * The file `hello` will be in the working directory

```bash
julien@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 julien julien 28 Sep 20 14:26 5-execute
-rw-rw-r-- 1 julien julien 23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$ ./hello
bash: ./hello: Permission denied
julien@ubuntu:/tmp/h$ ./5-execute 
julien@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 julien julien 28 Sep 20 14:26 5-execute
-rwxrw-r-- 1 julien julien 23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$
```

### 6. Multiple Permissions

Write a script that adds execute permission for owner and group, and read permission for others to `hello`.
   * The file `hello` will be in the working directory

```bash
julien@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 julien julien 36 Sep 20 14:31 6-multiple_permissions
-rw-r----- 1 julien julien 23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$ ./6-multiple_permissions 
julien@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 julien julien 36 Sep 20 14:31 6-multiple_permissions
-rwxr-xr-- 1 julien julien 23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$
```

### 7. Everybody!

Write a script that grants execution permission to everyone on `hello`.
   * The file `hello` will be in the working directory
   * You are not allowed to use commas for this script

```bash
$ ./7-everybody
```

### 8. James Bond

Write a script that sets `007` permission mode to `hello`.
   * Owner: no permission at all
   * Group: no permission at all
   * Other users: all the permissions
The file `hello` will be in the working directory You are not allowed to use commas for this script

```bash
julien@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 julien julien 28 Sep 20 14:40 8-James_Bond
-rwxr-x--x 1 julien julien 23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$ ./8-James_Bond 
julien@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 julien julien 28 Sep 20 14:40 8-James_Bond
-------rwx 1 julien julien 23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$
```

### 9. John Doe

Write a script that sets `hello`'s owner to `john` and group to `doe`.

```bash
-rwxr-x-wx 1 julien julien 23 Sep 20 14:25 hello
```
   * The file `hello` will be in the working directory
   * You are not allowed to use commas for this script

### 10. Look in the Mirror

Write a script that sets the mode of `hello` to match `olleh`.
   * The file `hello` will be in the working directory
   * The file `olleh` will be in the working directory

```bash
julien@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 julien julien 42 Sep 20 14:45 10-mirror_permissions
-rwxr-x-wx 1 julien julien 23 Sep 20 14:25 hello
-rw-rw-r-- 1 julien julien  0 Sep 20 14:43 olleh
julien@ubuntu:/tmp/h$ ./10-mirror_permissions 
julien@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 julien julien 42 Sep 20 14:45 10-mirror_permissions
-rw-rw-r-- 1 julien julien 23 Sep 20 14:25 hello
-rw-rw-r-- 1 julien julien  0 Sep 20 14:43 olleh
julien@ubuntu:/tmp/h$
```
Note: the mode of `olleh` will not always be 664. Make sure your script works for any mode.

### 11. Directories Permissions

Write a script that adds execute permission to all subdirectories.

```bash
julien@ubuntu:/tmp/h$ ls -l
total 20
-rwxrwxr-x 1 julien julien   24 Sep 20 14:53 11-directories_permissions
drwx------ 2 julien julien 4096 Sep 20 14:49 dir0
drwx------ 2 julien julien 4096 Sep 20 14:49 dir1
drwx------ 2 julien julien 4096 Sep 20 14:49 dir2
-rw-rw-r-- 1 julien julien   23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$ ./11-directories_permissions 
julien@ubuntu:/tmp/h$ ls -l
total 20
-rwxrwxr-x 1 julien julien   24 Sep 20 14:53 11-directories_permissions
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir0
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir1
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir2
-rw-rw-r-- 1 julien julien   23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$
```

### 12. Directory Permissions

Write a script that creates `my_dir` with `751` permissions.

```bash
julien@ubuntu:/tmp/h$ ls -l
total 20
-rwxrwxr-x 1 julien julien   39 Sep 20 14:59 12-directory_permissions
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir0
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir1
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir2
-rw-rw-r-- 1 julien julien   23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$ ./12-directory_permission s
julien@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 julien julien   39 Sep 20 14:59 12-directory_permissions
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir0
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir1
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir2
drwxr-x--x 2 julien julien 4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 julien julien   23 Sep 20 14:25 hello
julien@ubuntu:/tmp/h$
```

### 13. Change Group

Write a script that changes the group owner of `hello` to `school`.
   * The file `hello` will be in the working directory

```bash
julien@ubuntu:/tmp$ ls -l
total 24
-rwxrwxr-x 1 julien julien   34 Sep 20 15:03 13-change_group
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir0
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir1
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir2
drwxr-x--x 2 julien julien 4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 julien julien   23 Sep 20 14:25 hello
julien@ubuntu:/tmp$ sudo ./13-change_group 
julien@ubuntu:/tmp$ ls -l
total 24
-rwxrwxr-x 1 julien julien      34 Sep 20 15:03 13-change_group
drwx--x--x 2 julien julien    4096 Sep 20 14:49 dir0
drwx--x--x 2 julien julien    4096 Sep 20 14:49 dir1
drwx--x--x 2 julien julien    4096 Sep 20 14:49 dir2
drwxr-x--x 2 julien julien    4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 julien school   23 Sep 20 14:25 hello
julien@ubuntu:/tmp$
```

### 14. Change Owner and Group

Write a script that changes the owner to `vincent` and group to `staff` for all files.

```bash
julien@ubuntu:/tmp$ ls -l
total 24
-rwxrwxr-x 1 julien julien   36 Sep 20 15:06 14-change_owner_and_group
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir0
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir1
drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir2
drwxr-x--x 2 julien julien 4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 julien julien   23 Sep 20 14:25 hello
julien@ubuntu:/tmp$ sudo ./14-change_owner_and_group 
julien@ubuntu:/tmp$ ls -l
total 24
-rwxrwxr-x 1 vincent staff   36 Sep 20 15:06 14-change_owner_and_group
drwx--x--x 2 vincent staff 4096 Sep 20 14:49 dir0
drwx--x--x 2 vincent staff 4096 Sep 20 14:49 dir1
drwx--x--x 2 vincent staff 4096 Sep 20 14:49 dir2
drwxr-x--x 2 vincent staff 4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 vincent staff   23 Sep 20 14:25 hello
julien@ubuntu:/tmp$
```

### 15. Symbolic Link Permissions

Write a script that changes the owner and group of `_hello`.
   * The file `_hello` is in the working directory
   * The file `_hello` is a symbolic link

```bash
julien@ubuntu:/tmp$ ls -l
total 24
-rwxrwxr-x 1 julien julien   44 Sep 20 15:12 15-symbolic_link_permissions
-rw-rw-r-- 1 julien julien   23 Sep 20 14:25 hello
lrwxrwxrwx 1 julien julien    5 Sep 20 15:10 _hello -> hello
julien@ubuntu:/tmp$ sudo ./15-symbolic_link_permissions 
julien@ubuntu:/tmp$ ls -l
total 24
-rwxrwxr-x 1 julien julien      44 Sep 20 15:12 15-symbolic_link_permissions
-rw-rw-r-- 1 julien julien      23 Sep 20 14:25 hello
lrwxrwxrwx 1 vincent  staff    5 Sep 20 15:10 _hello -> hello
julien@ubuntu:/tmp$
```

### 16. If Only

Write a script that changes `hello`'s owner to `vincent` if it is owned by `guillaume`.
   * The file `hello` will be in the working directory

```bash
julien@ubuntu:/tmp$ ls -l
total 24
-rwxrwxr-x 1 julien    julien      47 Sep 20 15:18 16-if_only 
-rw-rw-r-- 1 guillaume julien      23 Sep 20 14:25 hello
julien@ubuntu:/tmp$ sudo ./16-if_only 
julien@ubuntu:/tmp$ ls -l
total 24
-rwxrwxr-x 1 julien julien      47 Sep 20 15:18 16-if_only 
-rw-rw-r-- 1 vincent  julien      23 Sep 20 14:25 hello
julien@ubuntu:/tmp$
```

---


Happy coding! 🌟

