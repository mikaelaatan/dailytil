## Linux Permissions
- Read, Write, Execute
- **SetUID or GetUID**: allows users/groups to run the file with the permission of the owner of the file
- **StickyBit**: anyone can write to file or folder but can't delete anything; only owner or root can delete

### Checking permissions

``` bash
$ ls -l ~/my_file

# output
-rw-r--r-- 1 mikaela mikaela 6140 Mar 10 12:30 getting-started-git.md

# (-) means regular file
# 9-bits represents the permissions in trio grouping
# 1st trio: permission of the owner
# 2nd trio: permission of group the files belong to
# 3rd trio: permission of all other users

```

### Modifying permissions

Adding permissions
``` bash
$ chmod <type>+<permission> <path to file>

# types:
# u- user
# g- group
# o- other users

$ chmod u+x my_cool_file

# permissions:
# The numerical equivalent of rwx:
# 4 for read or r
# 2 for write or w
# 1 for execute or x

$ sudo chmod 754 my_cool_file

# 7- user (rwx)
# 5- group (rx)
# 4- other users (r)

```

Removing permissions
``` bash
$ chmod u-x my_cool_file

# change plus to minus

```

### Special Permissions: SetUID, SetGID, StickyBit
- allows users to change files without root access 

SetUID
- S permission- allows users to run the file with the permission of the owner of the file
- viewed as `s` in the first trio of the permissions
``` bash
$ chmod u+s my_cool_file
$ chmod 4755 my_cool_file

# prepend 4 to the numerical permissions

```

SetGID
- viewed as `s` in the 2nd trio of the permissions
``` bash
$ chmod g+s my_cool_file
$ chmod 2755 my_cool_file

# prepend 2 to the numerical permissions

```

StickyBit
- anyone can write to file or folder but can't delete anything; only owner or root can delete
- viewed as `t` in the last bit of the permissions
``` bash
$ chmod +t my_cool_file
$ chmod 2755 my_cool_file

# prepend 1 to the numerical permissions

```

Source: Notes from [Google Operating Systems and You (Coursera)]([Operating Systems and You: Becoming a Power User | Coursera](https://www.coursera.org/learn/os-power-user))