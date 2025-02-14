# Shell, Init Files, Variables and Expansions ✨

<p align="center">
   <img src="https://github.com/user-attachments/assets/7d564981-cb81-43e7-819a-25ffcfc5bd72" width=40% height=40%/>
</p>

## Overview

Welcome to **Shell, Init Files, Variables and Expansions**! This repository contains a series of scripts designed to enhance your understanding of shell initialization files, environment variables, expansions, and arithmetic operations in a Unix-based system. These scripts were created as part of a learning project aimed at mastering these fundamental shell operations.

## Table of Contents

1. [Resources](#resources-)
2. [Learning Objectives](#learning-objectives-)
3. [Project Requirements](#project-requirements-)
4. [Setup](#setup-)
5. [Scripts & Usage](#scripts--usage-)
   - [0. Alias](#0-alias)
   - [1. Hello You](#1-hello-you)
   - [2. Path](#2-path)
   - [3. Paths](#3-paths)
   - [4. Global Variables](#4-global-variables)
   - [5. Local Variables](#5-local-variables)
   - [6. Create Local Variable](#6-create-local-variable)
   - [7. Create Global Variable](#7-create-global-variable)
   - [8. True Knowledge](#8-true-knowledge)
   - [9. Divide and Rule](#9-divide-and-rule)
   - [10. Love Exponent Breath](#10-love-exponent-breath)
   - [11. Binary to Decimal](#11-binary-to-decimal)
   - [12. Combinations](#12-combinations)
   - [13. Print Float](#13-print-float)
   - [14. Decimal to Hexadecimal](#14-decimal-to-hexadecimal)

---

## Resources ✨

Here are some useful materials to help you understand shell init files, variables, and expansions:

- **Expansions**
- **Shell Arithmetic**
- **Variables**
- **Shell initialization files**
- **The alias Command**
- **Technical Writing**

### Commands Covered:

```bash
printenv, set, unset, export, alias, unalias, ., source, printf
```

---

## Learning Objectives 🎯

By the end of this project, you should be able to:

### General
- Understand what happens when you type `$ ls -l *.txt`

### Shell Initialization Files
- Explain the purpose of `/etc/profile` and the `/etc/profile.d` directory
- Understand the role of the `~/.bashrc` file

### Variables
- Differentiate between local and global variables
- Understand reserved variables
- Create, update, and delete shell variables
- Explain the roles of reserved variables: `HOME`, `PATH`, `PS1`
- Understand special parameters
- Know what `$?` represents

### Expansions
- Understand and utilize expansions
- Differentiate between single and double quotes and their usage
- Perform command substitution using `$()` and backticks

### Shell Arithmetic
- Execute arithmetic operations in the shell

### The alias Command
- Create an alias
- List existing aliases
- Temporarily disable an alias

### Other Help Pages
- Execute commands from a file in the current shell

---

## Project Requirements 👋

- Allowed editors: `vi`, `vim`, `emacs`
- Scripts will be tested on **Ubuntu 20.04 LTS**
- All scripts must be exactly **two lines long** (`wc -l file` should print `2`)
- All files must end with a new line
- The first line of each script must be `#!/bin/bash`
- A `README.md` file describing each script
- No use of **&&, ||, or ;**
- No use of **bc, sed, or awk**
- All files must be executable (`chmod u+x filename.sh`)

---

## Setup ⚙️

To get started, clone this repository:

```bash
git clone https://github.com/yourusername/shell-init-files-variables-expansions.git
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

Each of the following exercises demonstrates the use of different shell commands related to init files, variables, and expansions:

### 0. Alias

Create a script that creates an alias.
  * Name: `ls`
  * Value: `rm -f *`
Example :
```bash
julien@ubuntu:/tmp/0x03$ ls
0-alias  file1  file2
julien@ubuntu:/tmp/0x03$ source ./0-alias 
julien@ubuntu:/tmp/0x03$ ls
julien@ubuntu:/tmp/0x03$ \ls
julien@ubuntu:/tmp/0x03$
```

### 1. Hello You

Create a script that prints `hello user`, where user is the current Linux user.
Example :
```bash
julien@ubuntu:/tmp/0x03$ id
uid=1000(julien) gid=1000(julien) groups=1000(julien),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),113(lpadmin),128(sambashare)
julien@ubuntu:/tmp/0x03$ ./1-hello_you 
hello julien
julien@ubuntu:/tmp/0x03$
```

### 2. Path

Add `/action` to the `PATH`. `/action` should be the last directory the shell looks into when looking for a program.
Example :
```bash
julien@ubuntu:/tmp/0x03$ echo $PATH
/home/julien/bin:/home/julien/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
julien@ubuntu:/tmp/0x03$ source ./2-path 
julien@ubuntu:/tmp/0x03$ echo $PATH
/home/julien/bin:/home/julien/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/action
julien@ubuntu:/tmp/0x03$
```

### 3. Paths

Create a script that counts the number of directories in the `PATH`.
```bash
julien@ubuntu:/tmp/0x03$ echo $PATH
/home/julien/bin:/home/julien/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
julien@ubuntu:/tmp/0x03$ . ./3-paths 
11
julien@ubuntu:/tmp/0x03$ PATH=/home/julien/bin:/home/julien/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:::::/hello
julien@ubuntu:/tmp/0x03$ . ./3-paths 
12
julien@ubuntu:/tmp/0x03$
```

### 4. Global Variables

Create a script that lists environment variables.
```bash
julien@ubuntu:/tmp/0x03$ source ./4-global_variables
CC=gcc
CDPATH=.:~:/usr/local:/usr:/
CFLAGS=-O2 -fomit-frame-pointer
COLORTERM=gnome-terminal
CXXFLAGS=-O2 -fomit-frame-pointer
DISPLAY=:0
DOMAIN=hq.garrels.be
e=
TOR=vi
FCEDIT=vi
FIGNORE=.o:~
G_BROKEN_FILENAMES=1
GDK_USE_XFT=1
GDMSESSION=Default
GNOME_DESKTOP_SESSION_ID=Default
GTK_RC_FILES=/etc/gtk/gtkrc:/nethome/franky/.gtkrc-1.2-gnome2
GWMCOLOR=darkgreen
GWMTERM=xterm
HISTFILESIZE=5000
history_control=ignoredups
HISTSIZE=2000
HOME=/nethome/franky
HOSTNAME=octarine.hq.garrels.be
INPUTRC=/etc/inputrc
IRCNAME=franky
JAVA_HOME=/usr/java/j2sdk1.4.0
LANG=en_US
LDFLAGS=-s
LD_LIBRARY_PATH=/usr/lib/mozilla:/usr/lib/mozilla/plugins
LESSCHARSET=latin1
LESS=-edfMQ
LESSOPEN=|/usr/bin/lesspipe.sh %s
LEX=flex
LOCAL_MACHINE=octarine
LOGNAME=franky
[...]
julien@ubuntu:/tmp/0x03$
```

### 5. Local Variables

Create a script that lists all local variables and environment variables, and functions.
```bash
julien@ubuntu:/tmp/0x03$ . ./5-local_variables
BASH=/bin/bash
BASHOPTS=checkwinsize:cmdhist:complete_fullquote:expand_aliases:extglob:extquote:force_fignore:histappend:interactive_comments:progcomp:promptvars:sourcepath
BASH_ALIASES=()
BASH_ARGC=()
BASH_ARGV=()
BASH_CMDS=()
BASH_COMPLETION_COMPAT_DIR=/etc/bash_completion.d
BASH_LINENO=()
BASH_REMATCH=()
BASH_SOURCE=()
BASH_VERSINFO=([0]="4" [1]="3" [2]="46" [3]="1" [4]="release" [5]="x86_64-pc-linux-gnu")
BASH_VERSION='4.3.46(1)-release'
CLUTTER_IM_MODULE=xim
COLUMNS=133
COMPIZ_CONFIG_PROFILE=ubuntu
COMP_WORDBREAKS=$' \t\n"\'><=;|&(:'
DBUS_SESSION_BUS_ADDRESS=unix:abstract=/tmp/dbus-Fg27Lr20bq
DEFAULTS_PATH=/usr/share/gconf/ubuntu.default.path
DESKTOP_SESSION=ubuntu
[...]
julien@ubuntu:/tmp/0x03$
```

### 6. Create Local Variable

Create a script that creates a new local variable.
  * Name: `BEST`
  * Value: `School`

### 7. Create Global Variable

Create a script that creates a new global variable.

Name: `BEST`
Value: `School`

### 8. True Knowledge

Write a script that prints the result of the addition of 128 with the value stored in the environment variable `TRUEKNOWLEDGE`, followed by a new line.
```bash
julien@production-503e7013:~$ export TRUEKNOWLEDGE=1209
julien@production-503e7013:~$ ./8-true_knowledge | cat -e
1337$
julien@production-503e7013:~$
```

### 9. Divide and Rule

Write a script that prints the result of `POWER` divided by `DIVIDE`, followed by a new line.
  * `POWER` and `DIVIDE` are environment variables
```bash
julien@production-503e7013:~$ export POWER=42784
julien@production-503e7013:~$ export DIVIDE=32
julien@production-503e7013:~$ ./9-divide_and_rule | cat -e
1337$
julien@production-503e7013:~$
```

### 10. Love Exponent Breath

Write a script that displays the result of `BREATH` to the power `LOVE`
  * `BREATH` and `LOVE` are environment variables
  * The script should display the result, followed by a new line
```bash
julien@production-503e7013:~/$ export BREATH=4
julien@production-503e7013:~/$ export LOVE=3
julien@production-503e7013:~/$ ./10-love_exponent_breath
64
julien@production-503e7013:~/$
```

### 11. Binary to Decimal

Write a script that converts a number from base 2 to base 10.
  * The number in base 2 is stored in the environment variable `BINARY`
  * The script should display the number in base 10, followed by a new line
```bash
julien@production-503e7013:~/$ export BINARY=10100111001
julien@production-503e7013:~/$ ./11-binary_to_decimal
1337
julien@production-503e7013:~/$
```

### 12. Combinations

Create a script that prints all possible combinations of two letters, except `oo`.
  * Letters are lower cases, from `a` to `z`
  * One combination per line
  * The output should be alpha ordered, starting with `aa`
  * Do not print `oo`
  * Your script file should contain maximum 64 characters
```bash
julien@ubuntu:/tmp/0x03$ echo $((26 ** 2 -1))
675
julien@ubuntu:/tmp/0x03$ ./12-combinations | wc -l
675
julien@ubuntu:/tmp/0x03$ 
julien@ubuntu:/tmp/0x03$ ./12-combinations | tail -303 | head -10
oi
oj
ok
ol
om
on
op
oq
or
os
julien@ubuntu:/tmp/0x03$
```

### 13. Print Float

Write a script that prints a number with two decimal places, followed by a new line.
  * The number will be stored in the environment variable `NUM`.
```bash
ubuntu@ip-172-31-63-244:~/0x03$ export NUM=0
ubuntu@ip-172-31-63-244:~/0x03$ ./13-print_float
0.00
ubuntu@ip-172-31-63-244:~/0x03$ export NUM=98
ubuntu@ip-172-31-63-244:~/0x03$ ./13-print_float
98.00
ubuntu@ip-172-31-63-244:~/0x03$ export NUM=3.14159265359
ubuntu@ip-172-31-63-244:~/0x03$ ./13-print_float
3.14
ubuntu@ip-172-31-63-244:~/0x03$
```

### 14. Decimal to Hexadecimal

Write a script that converts a number from base 10 to base 16.
  * The number in base 10 is stored in the environment variable `DECIMAL`
  * The script should display the number in base 16, followed by a new line
```bash
julien@production-503e7013:~/$ export DECIMAL=16
julien@production-503e7013:~/$ ./14-decimal_to_hexadecimal
10
julien@production-503e7013:~/$ export DECIMAL=1337
julien@production-503e7013:~/$ ./14-decimal_to_hexadecimal | cat -e
539$
julien@production-503e7013:~/$ export DECIMAL=15
julien@production-503e7013:~/$ ./14-decimal_to_hexadecimal | cat -e
f$
julien@production-503e7013:~/$
```
