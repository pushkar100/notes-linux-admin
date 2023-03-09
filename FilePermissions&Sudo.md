# File Permissions & `sudo` Command:

- [File Permissions & `sudo` Command:](#file-permissions----sudo--command-)
    + [Checking Permissions:](#checking-permissions-)
    + [Changing permissions:](#changing-permissions-)
      - [chmod 'octal' mode:](#chmod--octal--mode-)
    + [Changing Owner (of a file or directory):](#changing-owner--of-a-file-or-directory--)
    + [Changing Owner & Group (of a file or directory):](#changing-owner---group--of-a-file-or-directory--)


File Permissions set for 3 sets of users:
1. User (current/owner)
2. Group
3. Others

Each type of user has:
1. Read(r) 
2. Write(w)
3. Execute(x) permissions

- Execute for a folder means we can go into/access the folder.
- Execute for a file means we can run the program/execute the script/etc.

Denial of a permission is indicated by a `-`. Ex:
- `drwxr-xr--` => means that it is a directory(d), user has all 3 permissions(rwx), group has only read and execute permission(r-x), and others have only read permission(r--).

### Checking Permissions:
- `ls -l` => longlisting of files in a directory will show us the permissions it has.

Format Displayed:
1. Is Directory? and File permissions (user, group, others)
2. Owner of the file/dir (A user on the sytem)

### Changing permissions:

Use `chmod` which changes or modifies permissions.

- `chmod o-rx fileOrDirectoryPath` = Changes permissions for 'others' by removing read and execute permissions '-rx' (for others) on the mentioned File.

Above might not work sometimes. (Ex: chmod: `abc.txt`: Operation not permitted)

.. AND THAT'S BECAUSE WE DON'T HAVE THE AUTHORITY TO CHANGE OWNERSHIP. 

IN THIS CASE, WE WILL HAVE TO RUN THE COMMAND AS A 'SUPERUSER' (Therefore, prefix command with `sudo` which will run it as from the superuser - requires the password to superuser login.)

**Therefore:(Solution)**
- `sudo chmod o-rx fileOrDirectoryPath` = Changes permissions for 'others' by removing read and execute permissions '-rx' (for others) on the mentioned File.

Another Usage:
- `sudo chmod a=rx fileOrDirectoryPath` = Changes permissions for 'all(u,g,o)' by having only read and execute permissions(no write access).

Combining it for user, group and others. Ex: `chmod u=rwx,g=rx,o=r myfile`

#### chmod 'octal' mode:

Ex: `chmod 754 myfile`

Here the digits 7, 5, and 4 each individually represent the permissions for the user, group, and others, in that order. Each digit is a combination of the numbers 4, 2, 1, and 0:

- 4 stands for "read",
- 2 stands for "write",
- 1 stands for "execute", and
- 0 stands for "no permission."

So 7 is the combination of permissions 4+2+1 (read, write, and execute), 5 is 4+0+1 (read, no write, and execute), and 4 is 4+0+0 (read, no write, and no execute).

NOTE:
- `+` = Add permissions (Ex: `+rx` => add read and execute permissions)
- `-` = Remove permissions (Ex: `-wx` => remove write and execute permissions)
- `=` = Set permissions to only what's mentioned(on RHS of `=`) and remove un-mentioned permissions

NOTE:
- u = user
- g = group
- o = others
- a = all (u,g,o)

We may even combine them. Ex: 'ug' => user and group

NOTE:
- r = read
- w = write
- x = execute.

### Changing Owner (of a file or directory):

Refers to a user on the system with a login name. (Use `chown`)

Every file/dir is owned by some user on the system. The default user on the system id ID'ed as `root`.
- `chown userName fileOrDirectoryPath` = Changes the Ownership of mentioned file(s)/dir(s) to the mentioned User.

ABOVE MIGHT NOT WORK SOMETIMES. Ex: chown: changing ownership of `abc.txt`: Operation not permitted

.. AND THAT'S BECAUSE WE DON'T HAVE THE AUTHORITY TO CHANGE OWNERSHIP. 

IN THIS CASE, WE WILL HAVE TO RUN THE COMMAND AS A 'SUPERUSER' (Therefore, prefix command with `sudo` which will run it as from the superuser - requires the password to superuser login.)

**Therefore:(Solution)**
- `sudo chown userName fileOrDirectoryPath` = Changes the Ownership of mentioned file(s)/dir(s) to the mentioned User.

### Changing Owner & Group (of a file or directory): 

Refers to a user on the system with a login name. (Again, use `chown`)

- `chown userName:groupName fileOrDirectoryPath` = Changes the Ownership of mentioned file(s)/dir(s) to the mentioned User and the mentioned Group.

IF NOT PERMITTED THEN USE `sudo`:
- `sudo chown userName:groupName fileOrDirectoryPath` = Changes the Ownership of mentioned file(s)/dir(s) to the mentioned User and the mentioned Group.

NOTE: CHANGING USER OR GROUP OWNERSHIP => THEY (USER, GROUP) MUST EXIST!

NOTE: We can also use `chgrp` command to change group:
- `chgrp groupName fileOrdirectoryPath` = changes group of the file(s)/dir(s) to the mentioned group

If not permitted, use `sudo`:
- `sudo chgrp groupName fileOrdirectoryPath` = changes group of the file(s)/dir(s) to the mentioned group

`sudo` prefix can be used to run any command for which we don't have permissions (And not just for file commands, but any command)
