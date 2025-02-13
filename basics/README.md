# Learning Shell Basics
This project was about to initiate me to the Shell basics commands, how to navigate and to manipulate files and directories.
I used to create executables script with chmod.
All of the content listing below are done by resolving exercices.

## Content

0. [Current working directory](#current-working-directory)
1. [List it](#list-it)
2. [Bring me home](#bring-me-home)
3. [List files](#list-files)
4. [List more files](#list-more-files)
5. [List files digit only](#list-files-digit-only)
6. [First directory](#first-directory)
7. [Move that file](#move-that-file)
8. [First delete](#first-delete)
9. [First dir deletion](#first-dir-deletion)
10. [Back](#back)
11. [Lists](#lists)
12. [File type](#file-type)
13. [Symbolic link](#symbolic-link)
14. [Copy html](#copy-html)
15. [Lets move](#lets-move)
16. [Clean emacs](#clean-emacs)
17. [Tree](#tree)

-----------------------------------------------

0. ## Current working directory

Write a script that prints the absolute path name of the current working directory.

Example:

        $ ./0-current_working_directory
        /basics
        $

-------------------------------------------------

1. ### List it

Display the contents list of your current directory.

Example:

        $ ./1-listit
        Applications    Documents   Dropbox Movies Pictures
        Desktop Downloads   Library Music Public
        $

-------------------------------------------------

2. ### Bring me home

Write a script that changes the working directory to the user’s home directory.

  * You are not allowed to use any shell variables
Example:

        user@ubuntu:/tmp$ pwd
        /tmp
        user@ubuntu:/tmp$ echo $HOME
        /home/user
        user@ubuntu:/tmp$ source ./2-bring_me_home
        user@ubuntu:~$ pwd
        /home/user
        user@ubuntu:~$

-------------------------------------------------

3. ### List files

Display current directory contents in a long format

Example:

        $ ./3-listfiles
        total 40
        -rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:19 0-current_working_directory
        -rwxr-xr-x@ 1 sylvain staff 19 Jan 25 00:23 1-listit
        -rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:29 2-bring_me_home
        -rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:39 3-listfiles
        -rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:20 README.md
        $

------------------------------------------------------

4. ### List more files

Display current directory contents, including hidden files (starting with .). Use the long format.

Example:

        $ ./4-listmorefiles
        total 48
        drwxr-xr-x@ 6 sylvain staff 204 Jan 25 00:29 .
        drwxr-xr-x@ 43 sylvain staff 1462 Jan 25 00:19 ..
        -rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:19 0-current_working_directory
        -rwxr-xr-x@ 1 sylvain staff 19 Jan 25 00:23 1-listit
        -rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:29 2-bring_me_home
        -rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:39 3-listfiles
        -rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:41 4-listmorefiles
        -rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:20 README.md
        $

-------------------------------------------------

5. ### List files digit only

Display current directory contents.

  * Long format
  * with user and group IDs displayed numerically
  * And hidden files (starting with .)
Example:

        $ ./5-listfilesdigitonly
        total 56
        drwxr-xr-x@ 6 501 20 204 Jan 25 00:29 .
        drwxr-xr-x@ 43 501 20 1462 Jan 25 00:19 ..
        -rwxr-xr-x@ 1 501 20 18 Jan 25 00:19 0-current_working_directory
        -rwxr-xr-x@ 1 501 20 18 Jan 25 00:23 1-listfiles
        -rwxr-xr-x@ 1 501 20 19 Jan 25 00:29 2-bring_me_home
        -rwxr-xr-x@ 1 501 20 20 Jan 25 00:39 3-listfiles
        -rwxr-xr-x@ 1 501 20 18 Jan 25 00:41 4-listmorefiles
        -rwxr-xr-x@ 1 501 20 18 Jan 25 00:43 5-listfilesdigitonly
        -rwxr-xr-x@ 1 501 20 18 Jan 25 00:20 README.md
        $

----------------------------------------------------

6. ### First directory

Create a script that creates a directory named my_first_directory in the /tmp/ directory.

Example:

        $ ./6-firstdirectory
        $ file /tmp/my_first_directory/
        /tmp/my_first_directory/: directory
        $

--------------------------------------------------

7. ### Move that file

Move the file betty from /tmp/ to /tmp/my_first_directory.

Example:

        $ ./7-movethatfile
        $ ls /tmp/my_first_directory/
        betty
        $

-------------------------------------------------

8. ### First delete

Delete the file betty.

  * The file betty is in /tmp/my_first_directory
Example:

        $ ./8-firstdelete
        $ ls /tmp/my_first_directory/
        $

------------------------------------------------

9. ### First dir deletion

Delete the directory my_first_directory that is in the /tmp directory.

Example:

        $ ./9-firstdirdeletion
        $ file /tmp/my_first_directory
        /tmp/my_first_directory: cannot open `/tmp/my_first_directory' (No such file or                directory)
        $

------------------------------------------------

10. ### Back

Write a script that changes the working directory to the previous one.

        user@ubuntu:/tmp$ pwd
        /tmp
        user@ubuntu:/tmp$ cd /var
        user@ubuntu:/var$ pwd
        /var
        user@ubuntu:/var$ source ./10-back
        /tmp
        user@ubuntu:/tmp$ pwd
        /tmp

-------------------------------------------

11. ### Lists

Write a script that lists all files (even ones with names beginning with a period character, which are normally hidden) in the current directory and the parent of the working directory and the /boot directory (in this order), in long format.

Be careful with the /

------------------------------------------------

12. ### File type

Write a script that prints the type of the file named iamafile. The file iamafile will be in the /tmp directory when we will run your script.

Example :

        ubuntu@ip-172-31-63-244:~$ ./12-file_type
        /tmp/iamafile: ELF 64-bit LSB  executable, x86-64, version 1 (SYSV), dynamically               linked (uses shared libs), for GNU/Linux 2.6.24,                                               BuildID[sha1]=bd39c07194a778ccc066fc963ca152bdfaa3f971, stripped
Note that depending on the file, the output of your script will be different.

-----------------------------

13. ### Symbolic link

Create a symbolic link to /bin/ls, named __ls__. The symbolic link should be created in the current working directory.

        ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la
        total 144
        drwxrwxr-x  2 ubuntu ubuntu   4096 Sep 20 03:24 .
        drwxrwxrwt 12 root   root   139264 Sep 20 03:24 ..
        ubuntu@ip-172-31-63-244:/tmp/sym$./13-symbolic_link
        ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la
        total 144
        drwxrwxr-x  2 ubuntu ubuntu   4096 Sep 20 03:24 .
        drwxrwxrwt 12 root   root   139264 Sep 20 03:24 ..
        lrwxrwxrwx  1 ubuntu ubuntu      7 Sep 20 03:24 __ls__ -> /bin/ls

----------------------------

14. ### Copy html

Create a script that copies all the HTML files from the current working directory to the parent of the working directory, but only copy files that did not exist in the parent of the working directory or were newer than the versions in the parent of the working directory.

You can consider that all HTML files have the extension .html

-----------------------------

15. ### Lets move

Create a script that moves all files beginning with an uppercase letter to the directory /tmp/u.

You can assume that the directory /tmp/u will exist when we will run your script

        ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la
        total 148
        drwxrwxr-x  3 ubuntu ubuntu   4096 Sep 20 03:33 .
        drwxrwxrwt 12 root   root   139264 Sep 20 03:26 ..
        -rw-rw-r--  1 ubuntu ubuntu      0 Sep 20 03:32 My_file
        lrwxrwxrwx  1 ubuntu ubuntu      7 Sep 20 03:24 __ls__ -> /bin/ls
        -rw-rw-r--  1 ubuntu ubuntu      0 Sep 20 03:32 Elif_ym
        -rw-rw-r--  1 ubuntu ubuntu      0 Sep 20 03:32 random_file
        ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la /tmp/u
        total 8
        drwxrwxr-x 2 ubuntu ubuntu 4096 Sep 20 03:33 .
        drwxrwxr-x 3 ubuntu ubuntu 4096 Sep 20 03:33 ..
        ubuntu@ip-172-31-63-244:/tmp/sym$ ./15-lets_move
        ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la
        total 148
        drwxrwxr-x  3 ubuntu ubuntu   4096 Sep 20 03:33 .
        drwxrwxrwt 12 root   root   139264 Sep 20 03:26 ..
        lrwxrwxrwx  1 ubuntu ubuntu      7 Sep 20 03:24 __ls__ -> /bin/ls
        -rw-rw-r--  1 ubuntu ubuntu      0 Sep 20 03:32 random_file
        ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la /tmp/u
        total 8
        drwxrwxr-x 2 ubuntu ubuntu 4096 Sep 20 03:33 .
        drwxrwxr-x 3 ubuntu ubuntu 4096 Sep 20 03:33 ..
        -rw-rw-r-- 1 ubuntu ubuntu    0 Sep 20 03:32 My_file
        -rw-rw-r-- 1 ubuntu ubuntu    0 Sep 20 03:32 Elif_ym

-------------------------------

16. ### Clean emacs

Create a script that deletes all files in the current working directory that end with the character ~.

        ubuntu@ip-172-31-63-244:/tmp/sym$ ls
        main.c  main.c~  Makefile~
        ubuntu@ip-172-31-63-244:/tmp/sym$ ./16-clean_emacs
        ubuntu@ip-172-31-63-244:/tmp/emacs$ ls
        main.c
        ubuntu@ip-172-31-63-244:/tmp/emacs$

-------------------------------

17. ### Tree

Create a script that creates the directories welcome/, welcome/to/ and welcome/to/school in the current directory.

You are only allowed to use two spaces (and lines) in your script, not more.

        user@ubuntu:/tmp/h$ ls -l
        total 4
        -rwxrw-r-- 1 user user 44 Sep 20 12:09 17-tree
        julien@ubuntu:/tmp/h$ wc -l 17-tree 
        2 17-tree
        user@ubuntu:/tmp/h$ head -1 17-tree 
        #!/bin/bash
        user@ubuntu:/tmp/h$ tr -cd ' ' < 17-tree | wc -c # you do not have to understand               this yet, but the result should be 2, 1 or 0
        2
        user@ubuntu:/tmp/h$ ./17-tree 
        user@ubuntu:/tmp/h$ ls
        17-tree  welcome
        user@ubuntu:/tmp/h$ ls welcome/
        to
        user@ubuntu:/tmp/h$ ls -l welcome/to
        total 4
        drwxrwxr-x 2 user user 4096 Sep 20 12:11 school
        user@ubuntu:/tmp/h$
