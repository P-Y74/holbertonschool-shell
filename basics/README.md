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
