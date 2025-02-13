# Shell, Permissions
This project is about understand and how to use permissions.

## Content

0. [I am Betty](#i-a-betty)
1. [Who am I](#who-i-am)
2. [Groups](#groups)
3. [New owner](#new-owner)
4. [Empty](#empty)
5. [Execute](#execute)
6. [Multiple permissions](#multiple-permissions)
7. [Everybody](#everybody)
8. [James Bond](#james-bond)
9. [John Doe](#john-doe)
10. [Mirror permissions](#mirror-permissions)
11. [Directories permissions](#directories-permissions)
12. [Directory permissions](#directory-permissions)
13. [Change group](#change-group)
14. [Change owner and group](#change-owner-and-group)
15. [Symbolic link permissions](#symbolic-link-permissions)
16. [If only](#if-only)

--------------------------------

0. ### I am Betty

Create a script that switches the current user to the user betty.

  * You should use exactly 8 characters for your command (+1 character for the new line)
  * You can assume that the user betty will exist when we will run your script

        user@ubuntu:/tmp/h$ tail -1 0-iam_betty | wc -c
        9
        user@ubuntu:/tmp/h$

-------------------------

1. ### Who am I

Write a script that prints the effective username of the current user.

        user@ubuntu:/tmp/h$ ./1-who_am_i
        user
        user@ubuntu:/tmp/h$

------------------------

2. ### Groups

Write a script that prints all the groups the current user is part of.

        user@ubuntu:/tmp/h$ ./2-groups
        user adm cdrom sudo dip plugdev lpadmin sambashare
        user@ubuntu:/tmp/h$
Note: depending on the user, you will get a different output.

-----------------------

3. ### New owner

Write a script that changes the owner of the file hello to the user betty.

        user@ubuntu:/tmp$ ls -l
        total 4
        -rwxrw-r-- 1 user user 30 Sep 20 14:23 3-new_owner
        -rw-rw-r-- 1 user user  0 Sep 20 14:18 hello
        user@ubuntu:/tmp$ sudo ./3-new_owner 
        user@ubuntu:/tmp$ ls -l
        total 4
        -rwxrw-r-- 1 user user 30 Sep 20 14:23 3-new_owner
        -rw-rw-r-- 1 betty  user  0 Sep 20 14:18 hello
        user@ubuntu:/tmp$

---------------------

4. ### Empty

Write a script that creates an empty file called hello.

-----------------------

5. ### Execute

Write a script that adds execute permission to the owner of the file hello.

  * The file hello will be in the working directory

        user@ubuntu:/tmp/h$ ls -l
        total 8
        -rwxrw-r-- 1 user user 28 Sep 20 14:26 5-execute
        -rw-rw-r-- 1 user user 23 Sep 20 14:25 hello
        user@ubuntu:/tmp/h$ ./hello
        bash: ./hello: Permission denied
        user@ubuntu:/tmp/h$ ./5-execute 
        user@ubuntu:/tmp/h$ ls -l
        total 8
        -rwxrw-r-- 1 user user 28 Sep 20 14:26 5-execute
        -rwxrw-r-- 1 user user 23 Sep 20 14:25 hello
        user@ubuntu:/tmp/h$

-------------------------

6. ### Multiple permissions

Write a script that adds execute permission to the owner and the group owner, and read permission to other users, to the file hello.

  * The file hello will be in the working directory

        user@ubuntu:/tmp/h$ ls -l
        total 8
        -rwxrw-r-- 1 user user 36 Sep 20 14:31 6-multiple_permissions
        -rw-r----- 1 user user 23 Sep 20 14:25 hello
        user@ubuntu:/tmp/h$ ./6-multiple_permissions 
        user@ubuntu:/tmp/h$ ls -l
        total 8
        -rwxrw-r-- 1 user user 36 Sep 20 14:31 6-multiple_permissions
        -rwxr-xr-- 1 user user 23 Sep 20 14:25 hello
        user@ubuntu:/tmp/h$

--------------------------

7. ### Everybody

Write a script that adds execution permission to the owner, the group owner and the other users, to the file hello

  * The file hello will be in the working directory
  * You are not allowed to use commas for this script

        julien@ubuntu:/tmp/h$ ls -l
        total 8
        -rwxrw-r-- 1 julien julien 28 Sep 20 14:35 7-everybody
        -rw-r----- 1 julien julien 23 Sep 20 14:25 hello
        julien@ubuntu:/tmp/h$ ./7-everybody 
        julien@ubuntu:/tmp/h$ ls -l
        total 8
        -rwxrw-r-- 1 julien julien 28 Sep 20 14:35 7-everybody
        -rwxr-x--x 1 julien julien 23 Sep 20 14:25 hello
        julien@ubuntu:/tmp/h$

------------------

8. ### James Bond

Write a script that sets the permission to the file hello as follows:

  * Owner: no permission at all
  * Group: no permission at all
  * Other users: all the permissions
The file hello will be in the working directory. You are not allowed to use commas for this script

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

----------------------

9. ### John Doe

Write a script that sets the mode of the file hello to this :

        -rwxr-x-wx 1 julien julien 23 Sep 20 14:25 hello
  * The file hello will be in the working directory
  * You are not allowed to use commas for this script

--------------------

10. ### Mirror permissions

Write a script that sets the mode of the file hello the same as olleh’s mode.

  * The file hello will be in the working directory
  * The file olleh will be in the working directory

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
Note: the mode of olleh will not always be 664. Make sure your script works for any mode.

---------------------

11. ### Directories permissions

Create a script that adds execute permission to all subdirectories of the current directory for the owner, the group owner and all other users. Regular files should not be changed.

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

---------------------

12. ### Directory permissions

Create a script that creates a directory called my_dir with permissions 751 in the working directory.

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

--------------------------

13. ### Change group

Write a script that changes the group owner to school for the file hello

  * The file hello will be in the working directory
  * The script must be present on the github repository and on the sandbox on the folder /tmp

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

----------------------------

14. ### Change owner and group

Write a script that changes the owner to vincent and the group owner to staff for all the files and directories in the working directory.

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

----------------------

15. ### Symbolic link permissions

Write a script that changes the owner and the group owner of _hello to vincent and staff respectively.

  * The file _hello is in the working directory
  * The file _hello is a symbolic link

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

--------------------

16. ### If only

Write a script that changes the owner of the file hello to vincent only if it is owned by the user guillaume.

  * The file hello will be in the working directory

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
