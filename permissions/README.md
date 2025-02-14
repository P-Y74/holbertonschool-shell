# Shell, Permissions ✨

## Overview

Welcome to **Shell, Permissions**! This repository contains a collection of scripts aimed at mastering file permissions, user management, and access control in a Unix-based system. The goal is to become proficient in managing file and directory permissions using command-line tools.

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

```bash
$ ./0-change_user
```

### 1. Print Effective UID

Write a script that prints the effective user ID of the current user.

```bash
$ ./1-print_effective_uid
```

### 2. Groups

Write a script that prints all the groups the current user is part of.

```bash
$ ./2-groups
```

### 3. New Owner

Write a script that changes the owner of the file `hello` to `betty`.

```bash
$ ./3-new_owner
```

### 4. Empty File

Write a script that creates an empty file called `hello`.

```bash
$ ./4-empty_file
```

### 5. Execute Permission

Write a script that adds execute permission to `hello` for the owner.

```bash
$ ./5-execute_permission
```

### 6. Multiple Permissions

Write a script that adds execute permission for owner and group, and read permission for others to `hello`.

```bash
$ ./6-multiple_permissions
```

### 7. Everybody!

Write a script that grants execution permission to everyone on `hello`.

```bash
$ ./7-everybody
```

### 8. James Bond

Write a script that sets `007` permission mode to `hello`.

```bash
$ ./8-james_bond
```

### 9. John Doe

Write a script that sets `hello`'s owner to `john` and group to `doe`.

```bash
$ ./9-john_doe
```

### 10. Look in the Mirror

Write a script that sets the mode of `hello` to match `olleh`.

```bash
$ ./10-look_in_the_mirror
```

### 11. Directories Permissions

Write a script that adds execute permission to all subdirectories.

```bash
$ ./11-directories_permissions
```

### 12. Directory Permissions

Write a script that creates `my_dir` with `751` permissions.

```bash
$ ./12-directory_permissions
```

### 13. Change Group

Write a script that changes the group owner of `hello` to `school`.

```bash
$ ./13-change_group
```

### 14. Change Owner and Group

Write a script that changes the owner to `vincent` and group to `staff` for all files.

```bash
$ ./14-change_owner_and_group
```

### 15. Symbolic Link Permissions

Write a script that changes the owner and group of `_hello`.

```bash
$ ./15-symbolic_link_permissions
```

### 16. If Only

Write a script that changes `hello`'s owner to `vincent` if it is owned by `guillaume`.

```bash
$ ./16-if_only
```

---


Happy coding! 🌟

