## Linux User Management
**Superuser** - first user that gets created on Linux machine; only one SU or root account but any user can be granter SU privileges `sudo`

Change account in shell
```bash
$ sudo su -

```

View who has access to sudo
```bash
$ sudo cat /etc/group

root:x:0:
daemon:x:1:
bin:x:2:
sys:x:3:

# each line represents a different group
# fields: group name, group password, group ID, list of users in the group
```

View users in the machine
``` bash
$ sudo cat /etc/passwd

root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin

# fields: username, encrypted password, user ID, 

```

### Adding and removing users - Linux

Adding a new user
```bash
$ sudo useradd username

$ sudo passwd -e username

```

Deleting user
```bash
$ sudo userdel username

```

### Managing Passwords - Linux

Set a new password for a user
```bash
$ passwd username
Changing password for username.
(current) UNIX password:
Enter new UNIX password:
Retype new UNIX password:

# password is encrypted and stored in /etc/shadow
```

Force user to change password
```bash
$ passwd -e username

# expire a password and user needs to change password on next login

```

Source: Notes from [Google Operating Systems and You (Coursera)]([Operating Systems and You: Becoming a Power User | Coursera](https://www.coursera.org/learn/os-power-user))