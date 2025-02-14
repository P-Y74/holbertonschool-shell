# Shell Basics ✨

![Holberton School](https://upload.wikimedia.org/wikipedia/commons/8/8d/Holberton_School_logo.png)

## Overview

Welcome to **Shell Basics**! This repository contains a collection of scripts aimed at mastering fundamental shell commands and navigation techniques. The goal is to become proficient in using the command line for file management, directory manipulation, and script execution.

## Table of Contents

1. [Resources](#resources-)
2. [Learning Objectives](#learning-objectives-)
3. [Project Requirements](#project-requirements-)
4. [Setup](#setup-)
5. [Scripts & Usage](#scripts--usage-)
   - [0. Current Working Directory](#0-current-working-directory)
   - [1. List It](#1-list-it)
   - [2. Bring Me Home](#2-bring-me-home)
   - [3. List Files](#3-list-files)
   - [4. List More Files](#4-list-more-files)
   - [5. List Files Digit Only](#5-list-files-digit-only)
   - [6. First Directory](#6-first-directory)
   - [7. Move That File](#7-move-that-file)
   - [8. First Delete](#8-first-delete)
   - [9. First Dir Deletion](#9-first-dir-deletion)
   - [10. Back](#10-back)
   - [11. Lists](#11-lists)
   - [12. File Type](#12-file-type)
   - [13. Symbolic Link](#13-symbolic-link)
   - [14. Copy HTML](#14-copy-html)
   - [15. Let's Move](#15-lets-move)
   - [16. Clean Emacs](#16-clean-emacs)
   - [17. Tree](#17-tree)

---

## Resources ✨

Here are some useful materials to help you understand shell basics:

- **Introduction to Shell**
- **Navigation & File System**
- **Shell Commands & Shortcuts**
- **Man Pages & Documentation**
- **Understanding Shebang (**``**)**

### Commands Covered:

```bash
cd, ls, pwd, less, file, ln, cp, mv, rm, mkdir, type, which, help, man
```

---

## Learning Objectives 🎯

By the end of this project, you should be able to:

- Understand what **RTFM** and **Shebang** mean
- Differentiate between **Shell** and **Terminal**
- Efficiently navigate the file system using `cd`, `ls`, `pwd`
- Work with symbolic and hard links using `ln`
- Use wildcards, aliases, and history commands effectively
- Read and interpret **man pages**
- Utilize Bash keyboard shortcuts for efficiency
- Understand **LTS (Long-Term Support)** in Linux

---

## Project Requirements 📋

- Scripts must be exactly **two lines long** (`wc -l file` should print 2)
- The first line of each script must be `#!/bin/bash`
- Scripts must be executable (`chmod u+x filename.sh`)
- No use of **backticks**, `&&`, `||`, or `;`
- Tested on **Ubuntu 22.04 LTS**

---

## Setup ⚙️

To get started, clone this repository:

```bash
git clone https://github.com/yourusername/shell-basics.git
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

### 0. Current Working Directory

Print the absolute path of the current working directory.

```bash
$ ./0-current_working_directory
/basics
$
```

### 1. List It

Display the contents of the current directory.

```bash
$ ./1-listit
Applications Documents Downloads ...
$
```

### 2. Bring Me Home

Change the working directory to the user's home directory.

```bash
$ ./2-bring_me_home
$ pwd
/home/user
$
```

### 3. List Files

Display files in the current directory in long format.

```bash
$ ./3-listfiles
...
```

### 4. List More Files

Display all files, including hidden ones, in long format.

```bash
$ ./4-listmorefiles
...
```

### 5. List Files Digit Only

Display only files starting with a digit in long format.

```bash
$ ./5-listfilesdigitonly
...
```

### 6. First Directory

Create a directory named `my_first_directory` in `/tmp/`.

```bash
$ ./6-firstdirectory
$ ls /tmp/
...
```

### 7. Move That File

Move file `betty` into `/tmp/my_first_directory/`.

```bash
$ ./7-movethatfile
$ ls /tmp/my_first_directory/
betty
$
```

### 8. First Delete

Delete the file `betty` in `/tmp/my_first_directory/`.

```bash
$ ./8-firstdelete
$ ls /tmp/my_first_directory/
$
```

### 9. First Dir Deletion

Delete the directory `my_first_directory` in `/tmp/`.

```bash
$ ./9-firstdirdeletion
$ ls /tmp/
$
```

### 10. Back

Change the working directory to the previous one.

```bash
$ ./10-back
$ pwd
/home/user
$
```

### 11. Lists

List all files in the current directory, parent directory, and `/boot`.

```bash
$ ./11-lists
...
```

### 12. File Type

Print the type of a file named `iamafile`.

```bash
$ ./12-file_type
file iamafile
$
```

### 13. Symbolic Link

Create a symbolic link named `__ls__` to `/bin/ls`.

```bash
$ ./13-symbolic_link
$ ls -l __ls__
lrwxrwxrwx 1 user user ... __ls__ -> /bin/ls
$
```

### 14. Copy HTML

Copy all HTML files from current directory to the parent directory.

```bash
$ ./14-copy_html
$
```

### 15. Let's Move

Move all files beginning with an uppercase letter to `/tmp/u`.

```bash
$ ./15-lets_move
$
```

### 16. Clean Emacs

Delete all Emacs backup files (`*~`).

```bash
$ ./16-clean_emacs
$
```

### 17. Tree

Create directories `welcome/`, `welcome/to/`, `welcome/to/school` in current directory.

```bash
$ ./17-tree
$ tree
.
└── welcome
    └── to
        └── school
$
```

---


Happy coding! 🌟

