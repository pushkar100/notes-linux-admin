# Linux Administration Basics Notes:

Linux Administration Notes &amp; Quick Reference

- [Linux Administration Basics Notes:](#linux-administration-basics-notes-)
  * [What is LINUX?:](#what-is-linux--)
  * [Linux Directory Structure](#linux-directory-structure)
    + [Common Directories](#common-directories)
    + [Application Directory Structure](#application-directory-structure)
  * [The Shell](#the-shell)
    + [The Prompt](#the-prompt)
  * [The Super User](#the-super-user)
  * [Basic Linux Commands](#basic-linux-commands)
  * [Environment Variables](#environment-variables)
    + [PATH Environment Variable](#path-environment-variable)
  * [which command](#which-command)
  * [help option/flag:](#help-option-flag-)
  * [Linux Directories](#linux-directories)
    + [How to check the previous working directory](#how-to-check-the-previous-working-directory)
    + [Executing commands NOT FOUND in the $PATH](#executing-commands-not-found-in-the--path)
    + [Creating & Deleting Directories](#creating---deleting-directories)
    + [Listing Files and Directories](#listing-files-and-directories)
    + [tree command](#tree-command)
    + [Spaces in names](#spaces-in-names)
    + [File Permissions](#file-permissions)
      - [First character](#first-character)
      - [Remaining Characters can be Permission characters](#remaining-characters-can-be-permission-characters)
      - [Character meanings for Directories](#character-meanings-for-directories)
      - [Permission Categories](#permission-categories)
      - [Changing Permissions](#changing-permissions)
        * [Modifying permissions](#modifying-permissions)
        * [Change group permissions:](#change-group-permissions-)
  * [File Creation Mask](#file-creation-mask)
    + [umask command](#umask-command)
  * [find command](#find-command)
    + [The locate command](#the-locate-command)
  * [Viewing & Editing Files](#viewing---editing-files)
    + [Follow changes to a file in Real Time](#follow-changes-to-a-file-in-real-time)
    + [nano editor](#nano-editor)
    + [vi editor](#vi-editor)
    + [emacs editor](#emacs-editor)
    + [Graphical Editors](#graphical-editors)
  * [Delete Copy Move and Rename files](#delete-copy-move-and-rename-files)
  * [sort command](#sort-command)
  * [Create a collection of a group of files](#create-a-collection-of-a-group-of-files)
  * [Compress Files](#compress-files)
    + [Disk Usage Stats](#disk-usage-stats)
    + [tar and gzip](#tar-and-gzip)
  * [WildCards](#wildcards)
  * [Input Output and Redirection](#input-output-and-redirection)
    + [Redirection](#redirection)
    + [The Null Device](#the-null-device)
    + [Combining input and output redirection](#combining-input-and-output-redirection)
  * [Comparing two files](#comparing-two-files)
    + [diff Example](#diff-example)
    + [sdiff Example](#sdiff-example)
    + [vimdiff Example](#vimdiff-example)
  * [Searching in files and using pipes](#searching-in-files-and-using-pipes)
    + [Finding out the type of a file](#finding-out-the-type-of-a-file)
    + [Searching for strings in a binary file](#searching-for-strings-in-a-binary-file)
    + [Pipes or Pipelining](#pipes-or-pipelining)
    + [`cut` command](#-cut--command)
    + [Translating Characters](#translating-characters)
    + [Formatting output into columns](#formatting-output-into-columns)
    + [more and less commands](#more-and-less-commands)
  * [Copying files over the network](#copying-files-over-the-network)
    + [SCP](#scp)
    + [SFTP:](#sftp-)
  * [Customizing the Shell Prompt](#customizing-the-shell-prompt)
  * [Shell aliases](#shell-aliases)
  * [Environment variables](#environment-variables)
    + [Viewing all the environment variables](#viewing-all-the-environment-variables)
    + [Creating or modifying environment variables](#creating-or-modifying-environment-variables)
    + [Removing environment variables](#removing-environment-variables)
    + [Persisting the environment variables settings](#persisting-the-environment-variables-settings)
  * [Processes and job control](#processes-and-job-control)
    + [Displaying process information](#displaying-process-information)
      - [Options for ps](#options-for-ps)
      - [Killing a currently running foreground process](#killing-a-currently-running-foreground-process)
      - [Suspend a foreground process](#suspend-a-foreground-process)
      - [Background processes](#background-processes)
        * [Starting a background process](#starting-a-background-process)
    + [Listing jobs](#listing-jobs)
    + [Forcing processes into the background](#forcing-processes-into-the-background)
  * [Killing Processes](#killing-processes)
    + [Killing any process using PID](#killing-any-process-using-pid)
    + [Killing any process using job number:](#killing-any-process-using-job-number-)
    + [Signals have numbers associated with them](#signals-have-numbers-associated-with-them)
    + [Summary](#summary)
  * [Scheduling repeated jobs with cron](#scheduling-repeated-jobs-with-cron)
    + [Redirecting the output of the cron jobs](#redirecting-the-output-of-the-cron-jobs)
    + [Using multiple values](#using-multiple-values)
    + [crontab command](#crontab-command)
  * [Switching users and running commands as others](#switching-users-and-running-commands-as-others)
    + [Options for su](#options-for-su)
    + [User identification commands](#user-identification-commands)
    + [The sudo command](#the-sudo-command)
      - [Executing commands with sudo](#executing-commands-with-sudo)
      - [Switching users by using sudo su](#switching-users-by-using-sudo-su)
    + [Modifying the sudo configuration](#modifying-the-sudo-configuration)
  * [Shell history](#shell-history)
    + [Viewing history](#viewing-history)
    + [Setting the size of the history](#setting-the-size-of-the-history)
    + [Repeating commands from history](#repeating-commands-from-history)
    + [Reuse or pull out the arguments from the previous command](#reuse-or-pull-out-the-arguments-from-the-previous-command)
    + [Searching for commands](#searching-for-commands)
    + [Autocompletion](#autocompletion)
  * [Installing & managing software](#installing---managing-software)
    + [Package manager](#package-manager)
    + [The RPM format](#the-rpm-format)
    + [Installing packages not included in the package manager](#installing-packages-not-included-in-the-package-manager)
    + [General package info commands](#general-package-info-commands)
    + [Installing on Debian Distros with the APT package format](#installing-on-debian-distros-with-the-apt-package-format)
    + [The dpkg command used in addition to the `apt` utility](#the-dpkg-command-used-in-addition-to-the--apt--utility)
  * [The Linux boot process](#the-linux-boot-process)
    + [BIOS](#bios)
    + [Initial RAM Disk](#initial-ram-disk)
    + [The boot directory](#the-boot-directory)
      - [Viewing the boot directory](#viewing-the-boot-directory)
    + [The kernel ring buffer](#the-kernel-ring-buffer)
      - [Location of the kernel messages](#location-of-the-kernel-messages)
  * [Linux uses run Levels](#linux-uses-run-levels)
    + [Run levels](#run-levels)
    + [Setting the run level](#setting-the-run-level)
    + [systemd](#systemd)
  * [Rebooting](#rebooting)
  * [The system log](#the-system-log)
    + [Facilities](#facilities)
    + [Severities](#severities)
    + [rsyslog](#rsyslog)
    + [Caching vs non-caching](#caching-vs-non-caching)
  * [Disk management](#disk-management)
    + [Advantages of partitioning](#advantages-of-partitioning)
    + [Master Boot Record](#master-boot-record)
    + [GUID Partition Table](#guid-partition-table)
    + [Mount points](#mount-points)
    + [Mount partitions over existing data](#mount-partitions-over-existing-data)
    + [Mount points over other mount points](#mount-points-over-other-mount-points)
    + [fdisk to create and modify partitions on a disk](#fdisk-to-create-and-modify-partitions-on-a-disk)
      - [CREATE an MBR partition](#create-an-mbr-partition)
      - [View all the existing partitions](#view-all-the-existing-partitions)
      - [DELETE a partition](#delete-a-partition)
      - [SAVING all the partitions added or deleted in the fdisk utility](#saving-all-the-partitions-added-or-deleted-in-the-fdisk-utility)
      - [QUITTING without Saving](#quitting-without-saving)
      - [CREATING a GPT Partition](#creating-a-gpt-partition)
    + [File systems](#file-systems)
      - [Create a file system](#create-a-file-system)
    + [Mounting a device partition](#mounting-a-device-partition)
      - [Viewing the currently mounted file systems](#viewing-the-currently-mounted-file-systems)
      - [Unmount a file System](#unmount-a-file-system)
      - [Preparing a swap space](#preparing-a-swap-space)
    + [The file system table](#the-file-system-table)
      - [Viewing labels and UUIDs of file systems](#viewing-labels-and-uuids-of-file-systems)
      - [Labelling a file system](#labelling-a-file-system)
  * [Managing users and groups](#managing-users-and-groups)
    + [The root account](#the-root-account)
    + [Passwords are stored in a shadow file](#passwords-are-stored-in-a-shadow-file)
    + [UIDs](#uids)
    + [GIDs](#gids)
    + [Comment field](#comment-field)
    + [Home directory](#home-directory)
    + [Shell](#shell)
    + [The /etc/shadow file](#the--etc-shadow-file)
    + [Creating a user account](#creating-a-user-account)
    + [Create a password for the created user](#create-a-password-for-the-created-user)
    + [System or application accounts](#system-or-application-accounts)
      - [The -m option](#the--m-option)
    + [Deleting an account](#deleting-an-account)
    + [Mpdify an existing account](#mpdify-an-existing-account)
    + [Group details and creation](#group-details-and-creation)
    + [The /etc/gshadow file](#the--etc-gshadow-file)
      - [Create groups](#create-groups)
      - [Delete a group](#delete-a-group)
      - [Modify a group:](#modify-a-group-)
  * [Special permission modes](#special-permission-modes)
    + [The setuid bit](#the-setuid-bit)
      - [Security measures](#security-measures)
      - [Octal permissions](#octal-permissions)
      - [Adding the setuid attribute to a file](#adding-the-setuid-attribute-to-a-file)
      - [Removing the setuid attribute from a file](#removing-the-setuid-attribute-from-a-file)
      - [Find all the files on the system that have setuid set](#find-all-the-files-on-the-system-that-have-setuid-set)
    + [The setgid bit](#the-setgid-bit)
      - [Examples of commands using this setgid bit](#examples-of-commands-using-this-setgid-bit)
      - [Finding setgid files](#finding-setgid-files)
      - [Adding setgid permission](#adding-setgid-permission)
      - [Removing the setgid attribute from a file](#removing-the-setgid-attribute-from-a-file)
      - [Adding both setuid and setgid](#adding-both-setuid-and-setgid)
    + [The sticky bit](#the-sticky-bit)
      - [Adding the sticky bit](#adding-the-sticky-bit)
      - [Removing the sticky bit](#removing-the-sticky-bit)
      - [Reading the ls command output](#reading-the-ls-command-output)
  * [Networking](#networking)
    + [TCP/IP:](#tcp-ip-)
      - [IPv4 Classes](#ipv4-classes)
      - [Classless Inter-Domain Routing](#classless-inter-domain-routing)
      - [Reserved private address space](#reserved-private-address-space)
      - [Knowing the host computer IP address](#knowing-the-host-computer-ip-address)
      - [Another way to determine the host IP address](#another-way-to-determine-the-host-ip-address)
      - [DNS Hostnames](#dns-hostnames)
      - [Domains](#domains)
      - [Viewing the hostname](#viewing-the-hostname)
      - [Setting the hostname](#setting-the-hostname)
      - [Resolving DNS names](#resolving-dns-names)
      - [The hosts file](#the-hosts-file)
  * [DHCP static and dynamic addressing](#dhcp-static-and-dynamic-addressing)
    + [Ports](#ports)
    + [DHCP](#dhcp)
      - [Configuring a DHCP Client](#configuring-a-dhcp-client)
      - [Configuring an Ubuntu based System](#configuring-an-ubuntu-based-system)
    + [GUI or TUI Tools for networking](#gui-or-tui-tools-for-networking)
  * [Network troubleshooting](#network-troubleshooting)
    + [Test connectivity to a host with ping](#test-connectivity-to-a-host-with-ping)
    + [Testing connectivity over Hops](#testing-connectivity-over-hops)
      - [Output of traceroute](#output-of-traceroute)
      - [Alternative to traceroute](#alternative-to-traceroute)
    + [The netstat command](#the-netstat-command)
    + [Packet sniffing with tcpdump](#packet-sniffing-with-tcpdump)
    + [The obsolete telnet command](#the-obsolete-telnet-command)
  * [Connecting via SSH to a Linux Virtual Machine](#connecting-via-ssh-to-a-linux-virtual-machine)

## What is LINUX?:

Collection of Software that makes up an Operating System.

Linux OS = Linux Distribution 

A distribution differs from others in the type of software that it contains for a particular application. Ex: Different Linux distributions might have different default browsers, but all have a browser.

Distros/Flavors = Distributions. Ex: Red Hat Enterprise Linux, Ubuntu (Most Popular).

Red Hat = Popular in Banks, Airlines, Telecom and Healthcare sectors. (Red Hat - Need to pay for license.) 

Free Version of Red Hat for personal use = CentOS - A free brand of Red Hat Linux

Ubuntu = Popular with Startups, SaaS, Social Networks, Cloud Based.

Linux Kernel = Core of the OS (ALL Distros have the SAME Linux Kernel)

Linux Kernel + Applications = A Linux Distro.

(Other Distros: Linux Mint, Debian, Mageia, openSUSE, Fedora, ArchLinux, Slackware.)

NOTE: Distros are only slightly different from each other. Linux kernel is at the core of every distro, so the main concepts are the same for all and learning to do something in one distro is not very different from trying to do the same thing in another distro.

## Linux Directory Structure

Linux Directories === Windows Folders (Folders and Directories are used interchangeably.)


### Common Directories

**8 'must know' directories!**

- `/` => "root" (or, just `slash`) is the top level of the file system hierarchy.
- `/bin` => Contains binaries or executable programs.
- `/etc` => System Configuration Files
- `/home` => Home Directories (of the users on the system)
- `/opt` => Optional or Third Party Software (Ex: `Google Earth`s files and executables)
- `/tmp` => Temporary space, usually cleared on reboot(DONT have important stuff that you want to SAVE)
- `/usr` => User related programs.
- `/var` => Variable Data, most notable being the `log files` (system log files.)

Directories can have important sub-directories too: Example:-
- `/usr` :=
    - `/usr/bin` = Stores binaries/executables of user programs.
    - `usr/lib` = User libraries.

- `/home` :=	
    - `/home/pushkar` = Refers to the home folder of 'pushkar', a system user. (~)
    - `/var/log` = The variables directory containing a subdirectory 'log' that holds system log messages.

Other Important Directories:
- `/boot` => Contains files needed to boot the operating system.
- `/cdrom` (or) `/mount` (or) `/mnt` => Mount-point for CD-ROMs/removable media/external file systems.
- `/cgroup` => Control groups hierarchy.
- `/dev` => Device Files, typically controlled by Operating Sytem and System Administrators.
- `/export` => Shared file systems.
- `/lib` (or) `/lib64` => System libraries (or) System libraries(64bit).
- `/lost+found` => Used by OS to recover files after a file system check has been performed.
- `/proc` => Provides information about running processes.
- `/sbin` => System administration binaries.
- `/selinux` => Displays information about SELinux.
- `/sys` => Used to display and sometimes configure the devices known to the Linux Kernel.

Some Server Related Directories:
- /srv => Contains data which is served by the system.
- /srv/www => Contains Web Server files.
- /srv/ftp => Contains FTP files.

### Application Directory Structure

- Third Party Applications can be in `/usr/local` Directory:
Some applications that are NOT BUNDLED(Third Party) with the Linux OS by default are stored in the: `/usr/local` directory. These application directories have their own Linux-Likes sub-directory structure. Ex: 
 
 - `/usr/local/<application-name>/etc` => Application's configuration files(at runtime).
 - `/usr/local/<application-name>/bin` => Application's binary(executable) files.
 - `/usr/local/<application-name>/log` => Application's log files(execution log messages).

- Third Party Applications can also be in `/opt` Directory. Ex:

- `/opt/<application-name>/bin`
- `/opt/<application-name>/etc`
- `/opt/<application-name>/lib`
- `/opt/<application-name>/log`, ... etc.


NOTE:
- Sometimes, even though third-party applications get installed in `usr/local` or `/opt`, they can save/install some of their files in Other Directories, too. Ex: 
	- `/etc/opt/<application-name>`
	- `/var/opt/<application-name>`

- Sometimes when third-party applications are installed, they are not given their own directory structure, but instead they are installed in a 'Shared' Manner. Ex:
	- `/usr/local/bin/<application-name>`
	- `/usr/local/etc/<application-name>.conf`
	- `/usr/local/lib/<application-name>.so`

- We could use organisation/company name and store all the application(s)' files belonging to a particular organization under one folder. Ex:
	- `/opt/<organization-name>/etc` (or) `/opt/<organization-name>/<application-name/etc`,
	- `/opt/<organization-name>/bin` (or) `/opt/<organization-name>/<application-name/bin`,
	- `/opt/<organization-name>/lib` (or) `/opt/<organization-name>/<application-name/lib`

The Google Example: `/opt/google` | `/opt/google/chrome` | `/opt/google/earth`

## The Shell

It's the Default Interface to Linux. Programs that accepts commands and executes them. Also called a Command Line Interpreter.

Command Line is more powerful that GUI. There will always bea command line. Server Distributions do NOT include GUIs. Desktop Distributions have both GUI and CLI.

### The Prompt
Waits for user to do something(Execute some command). Typically, for normal users the prompt ends with '$' and for a superuser with a '#' (pound). Ex:
- `[pushkar@linuxsvr ~]$`
- `[pushkar@linuxsvr ~]#`

The '~' (tilde) represents your (the user's) HOME directory (Ex: `/home/pushkar`)

Shell prompts can be customized (change in appearance and information it displays)

## The Super User

**`root` account**

superuser/root account is ALL POWERFUL. All other NORMAL accounts can only do a SUBSET of the things that a superuser can do. (Note: root/superuser account is NOT to be confused with the root(/) directory).

- Root access: typically restricted to system administrators. Root access maybe required to install, start or stop an application. Day to day activities are usually performed from a NORMAL account(Not root account).

Note: sometimes you may have a root access and a normal account as well. ROOT ACCOUNT'S HOME FOLDER EXPANDS TO: `/root`  (= `~root`)

Note: Some services have THEIR OWN ACCOUNTS (like `ftp`): And hence, their own HOME folder. Ex: `/srv/ftp`  (= `~ftp`)

## Basic Linux Commands

Commands are case-sensitive.

- `ls` = List directory contents 
- `cd` = Changes the current directory
- `pwd` = Displays present working directory
- `cat` = Concatenates and Displays files
- `echo` = Displays arguments to the screen (variables/string arguments/both)
- `man` = Displays the online manual
- `exit` = Exits the shell or your current session
- `clear` = Clears the screen
- `diff file1 file2` = Displays the differences between two files.

- `man` command - screen keys:
  - `<ENTER>` => Scrolls down one Line at a time.
  - `<SPACEBAR>` => Scrolls down one Page at a time.
  - `G` (shift-g) => Scrolls down to the Bottom of the man output.
  - `g` => Scrolls down to the Top of the man output.
  - `q` => Quits the man pages application.

## Environment Variables

They are storage locations containing `name` and `value` pairs. They are typically in UPPERCASE.

Access environment variable contents by executing: `echo $VAR_NAME`

### PATH Environment Variable

PATH is an environment variable. It Contains a list of directories, separated by a colon (:).

It controls the 'command search path' = Means that whenever we enter a command at the command line, the system searches for that command in the command paths existing inside the $PATH variable. If it finds it, executes the command, else moves onto the next path and searches for it there and so on. If command is not found in any of these directories, it returns a command-not-found error.

Ex:
- `echo $PATH` => /usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/git/bin:/usr/local/Cellar/mongodb/3.2.4/bin:/Library/Frameworks/Python.framework/Versions/3.5/bin

(Searches for commands in every directory separated by a colon starting from the first one that is listed).

Note: If the same command exists inside multiple paths, then the one found in an earlier path is executed for that command.

## which command

**`which`**

Searches for the path of a command. (Location of the file which runs on the command execution). Ex: 
- `which cat` => /bin/cat
- `which cd` => /usr/bin/cd

## help option/flag:

**`--help`**

Prints a brief description of the command on the terminal. Ex:
- `ls --help`

(Sometimes, even `-h` works)

Use `man <command>` if `<command> --help` does NOT work.

## Linux Directories

Containers for other files and directories. They give a tree like structure to the file system. Can be accessed by 'name' or a 'shortcut'(symbolic link or soft link)

- `.` => current working directory.
- `..` => parent working directory.
- `-` => Usually refers to the previous working directory.

Ex: `cd -` => changes directory to the previous working directory.

NOTE: `ls -` does NOT work!

### How to check the previous working directory

`$OLDPATH` is an environment variable holding the path of the previous wroking directory. Ex:
- `echo $OLDPATH` => '/home'

### Executing commands NOT FOUND in the $PATH

(Also works for directories found in $PATH)

- We can use the FULL(ABSOLUTE) PATH of the command (location of the command) to execute it.

(Can be used to execute shell scripts also)

Syntax: `/full/path/to/command`

Ex:
- `/bin/cat datafile.txt` => '/bin/cat' is the full path of the `cat` command. (datafile.txt is in CWD)

- Use `./command` to execute the command residing in/relative to the current working directory.

(Can be used to execute shell scripts also)

Syntax: `./relative/path/to/command` (`.` represents PWD)

Ex:
- `./myscript.sh` => Executees myscript.sh that is in the current directory(.) .

### Creating & Deleting Directories

- `mkdir directory` => Create an Empty directory.
- `rmdir directoty` => Remove/Delete an Empty directory.
- `rm -rf directory` => Forcibly delete a directory(empty or not, all contents deleted - recursively)

- `mkdir -p directory` => Create Empty directories along with Parent directories(if not existing).

Ex:
- `mkdir -p one/two/three` => Creates an empty directory `one` in te CWD containing directory 'two' which contains directory `three`

- `rmdir -p directory` => Deletes empty directories including the specified empty parent directories. 

Ex:
- `rmdir -p one/two/three` => Deletes the nested empty directories `one`, `two` and `three`

NOTE: When you delete something from the CLI, it's gone forever. NO TRASH! from which we can retrieve

### Listing Files and Directories

- `ls -l` => Long Listing (Permissions, number of links, owner, group, file size in bytes, last modification time, file name)
- `ls -a` => List Hidden files as well (files that begin with a '.' / period) 
- `ls -F` => Reveals file types 

If name "ends" in: `/` => Directory, `@` or  `->` => Link, `*` => Executable.

- `ls -t` => List files by time. (Most recently modified file first)
- `ls -r` =? List files in reverse order.
- `ls -R` => Lists files Recursively. (Files of subdirectories and their subdirectories .. so on)

Others:
- `ls -d` => List Directory names but not contents (of the listed directories).
- `ls --color` => Colorize the output.

### tree command

**`tree`**

Similar to `ls -R`. But, it's more of a visual output only. (Using tree-like lines) Ex:
- `tree -d` => List Directories only.
- `tree -C` => Colorize the output.

(`tree` command may not be available as a command by default. Will need to add it.)

### Spaces in names

**(file or directory names)**

1. Spaces have to be escaped(Ex: `cd /home/pushkar/Technical\ Notes`)

(or)

2. Use quotes('' or  "") (Ex: `cd 'My Notes.txt'`) 

Instead, try using: '-' (dashes), '_' (underscores), or camelCase. (Try to avoid spaces while naming!)

### File Permissions

Ex: `-rwx-wxr--` => type-of-file(1CHAR) owner-perms(3CHAR)  group-perms(3CHAR) other-perms(3CHAR)

#### First character 

Refers to the **type of file**?
- `-` => Regular File
- `d` => Directory File
- `l` => Symbolic Link

#### Remaining Characters can be Permission characters

- `r` => Read Permission (View Contents of File)
- `w` => Write Permission (Modify or Change Contents of File)
- `x` => Execute Permission (Run the File as a Program)

'-' means that corresponding permission has been denied

#### Character meanings for Directories

**'r', 'w', and 'x'**

- `r` => Allows File Names inside the Directory to be read.
- `w` => Allows Entries to be Modififed within the Directory.
- `x` => Allows access to Contents and MetaData for Entries.

#### Permission Categories

- `u` => user 
- `g` => group 
- `o` => other
- `a` => all

- Groups(g): Every user -> Belongs to at least one group. A user maybe part of multiple groups. Groups are used to organize users.

Check all the groups which a user belongs to: `groups` (or) `id -Gn` (Same output for both)

#### Changing Permissions

`chmod`, `chgrp`, and `chown` commands.
- ugoa: Category (ctgry)
- +-=: add, subtract or set permissions (oprtr)
- rwx: read, write, & execute (prmssn)

##### Modifying permissions

**`chmod`**

- Symbolic Notation: `chmod <ctgry><oprtr><prmssn(s)> fileOrDirectory`. Ex:
	- `chmod g+w data-file.txt`, (Add)
	- `chmod a=r data-file.txt`, (Set)
	- `chmod g+w,o-x data-file.txt` (Multiple) ... etc.

- Octal Notation: `chmod <user-octal><group-octal><other-octal> fileOrDirectory`. Read(r) = 4, Write(w) = 2, Execute(x) = 1. Therefore: 
	- 7 (all permissions: read, write and execute)
	- 6 (read and write)
	- 5 (read and execute)
	- 4 (read),
	- 3 (write and execute)
	- 2 (write)
	- 1 (execute)]

Ex:
- `chmod 761 data-file.txt`, (rwx for user, only rw for group, only x for others)
- `chmod 400 data-file.txt`, (read for user, no permissions for group or others)

Common octal combos: 700, 755, 664, 660, 644

Don't give 777 permission => Gives everyone access to everything about that file. (Malicious code can modify permissions once again (removing you, perhaps) or modifying file or directory contents in ways you did expect.)

##### Change group permissions:

**`chgrp`**

Changes the group that the file belongs to: `chgrp <groupname> fileOrDirectory`

Ex:
- `chgrp sales sales-data.txt` (For example, we can even move the file to the shared folder '/usr/local/sales' so that people belonging to the sales group can edit the file there.)

NOTE: IF FILE PERMISSIONS SEEM CORRECT BUT YOU STILL CAN'T DO WHAT YOU WANT TO DO, CHECK THE DIRECTORY PERMISSIONS, THEN THE PARENT DIRECTORY PERMISSIONS.. AND SO ON UNTIL YOU FIND THE PERMISSION THAT NEEDS TO BE UNBLOCKED OR UNTIL YOU REACH THE ROOT(/) DIRECTORY.

## File Creation Mask

**umask**

The file creation mask decides what permissions must a file or directory have (by default) when it is created!.

If no mask is set:
- `777` => For Directories,
- `666` => For Files

### umask command

**`umask`**

Syntax: `umask [-S] [mode]`  (-S stands for 'symbolic notation')

`umask` "subtracts" permissions (opposite of `chmod`): Ex: If base is '777' and mask is '022', it would subtract 022 from 777. So, new permission = 755. (umask of 002 is ideal for working with groups since it gives your group permission to work with files)

`umask` sometimes needs to MAKE APPROXIMATIONS: Ex: Base = 666 and umask = 007 then final file permission is '660' (and not 66-1)

Usage Examples:
- `umask` => View the current umask setting (Ex: 0022)
- `umask -S` => View the current umask setting in Symbolic Notation (Ex: u=rwx,g=rx,o=rx [Displays the allowed permissions])

- `umask 002` => Changes the umask to 002 (popular way of changing permissions)
- `umask -S u=rwx,g=rx,o=rx`

Note: Usually in `umask` and `chmod` the 4th MSbit is ignored. Ex: 0644 = 644, 0022 = 022. But, The 4th MSBit can sometimes denote Special Modes: Ex: 
1. setuid, 
2. setgid, 
3. sticky [Covered Later]

## find command

**`find`**

Syntax: `find [path...] [expression]`

Recursively finds files in the path that match the expression. If no arguments are supplied, it finds all files in the current directory. (Ex: `find`)

Options:
- `-name pattern` => Finds files and Directories that match that pattern.
- `-iname pattern` => Like name, but ingores case.
- `-ls` => Perform an `ls` on each of the found items.

- `-mtime days` => Finds files that are 'days' old. *('+' => More than, '-' Less than )*
- `-size nums` => Find files that are size of 'num'. *('+' => More than, '-' Less than )*
- `-newer file` => Find files that are newer than 'file'
- `-type d` => Find files that are of type `d` (directory) [@ => links, * => executable]

- `exec <command> {} \;` => Run 'command' against all the files that are found.

Examples:
- `find` => Recursively lists all files under the current directory.
- `find /sbin -name makedev` = > Searches for files named 'makedev' inside '/sbin' directory.
- `find /sbin -iname makedev` = > Searches for files named 'makedev' inside '/sbin' directory(IGNORE CASE)
- `find /sbin -name makedev` = > Searches for files named 'makedev' inside '/sbin' directory.
- `find /sbin -name *v` = > Searches for files ending 'v' inside '/sbin' directory.
- `find /sbin -name makedev` = > Searches for files named 'makedev' inside '/sbin' directory.

- `find . -mtime +10 -mtime +13` = > Searches for files more than 10 days old but less than 13 days old inside current(.) directory.

- `find . s* -ls` => Recursively find anything that starts with 's' in CWD(.) and perform `ls` on it.
- `find . -size +1M` => Recursively find files in CWD(.) that are 1 MegaByte or larger. (K = kilo, G = giga)

- `find . -newer file.txt` => Searches for files that are newer than the file.txt file(modif. time-wise)

- `find . exec file {} \;` => Finds all files in the CWD and executes command 'file' against all of them.
 
### The locate command

**`locate`**

Syntax: `locate pattern`

Faster than find. Queries an index(adv.), but results are NOT in real-time.(disadv.) May NOT be enabled on all systems.

## Viewing & Editing Files

Basic commands:
- `cat file` => Display the contents of a file.
- `more file` => Browse through a text file.
- `less file` => Display the more than the 'more' command (less is actually more!) -> 'q' to exit.
- `head [-x] file` => Output the top portion(x lines) of the file (Default: 10 lines)
- `tail [-x] file` => Output the bottom portion(x lines) of the file (Default: 10 lines)

### Follow changes to a file in Real Time

**`tail -f file` => follow the file**

To view the changes to a file in real-time, use `tail -f` but not 'cat'(not real-time).

Ex: log files being written to -> use 'tail'on that log file : tail gets updated as file grows (to exit press 'CTRL-C')

Browsing through a 'more' or 'less' command screen => Same controls as in 'man' pages (Refer 'man')

### nano editor

**`nano`**

Small text editor. Easy to learn and use. Control commands appear on the screen itself. Not very powerful.

Open a text file in `nano`: `nano fileName`


### vi editor

**`vi`**

More powerful than 'nano'. Requires a learning curve. Commands are Not intuitive.

- `vi [file]` => Edit file
- `vim [file]` => Same as `vi` but improved/has more features.
- `view [file]` => Starts vim in 'read-only' mode.

`vi` has three modes: 
1. Normal(Command) 
2. Insert 
3. Line(Visual?)

`vi` commands:
- Movement:
	- `k` - up one line
	- `j` - down one line
	- `h` - left one character
	- `l` - right one character
	- `w` - right one word
	- `b` - left one word
	- `^` - go to the beginning of line
	- `$` - go to the end of line

- Inserting Text:
	- `i` - insert at cursor position
	- `I` - insert at the beginning of line
	- `a` - append after cursor position
	- `A` - append at the end of line
	- `o` - appends new(empty) line Below current line and moves cursor to it
	- `O` - appends new(empty) line Above current line and moves cursor to it

- `vi` Line Mode:
	- `:w` - Writes(Saves) file 
	- `:w!` - Forces the file to be saved
	- `:q` - Quit(come out of vi)
	- `:q!` - Quit without saving changes (force quit)
	- `:wq` - Write and quit
	- `:wq!` - Write and quit forcefully
	- `:x` - same as ':wq'
	- `:n` - go to line 'n' (Ex: ':50' goes to line 50)
	- `:$` - Positions cursor on the last line
	- `:set nu` - Turn On line numbering
	- `:set nonu` - Turn Off line numbering
	- `:help [subcommand]` - Get Help

- Deleting Text:
	- `x` - delete a character (at cursor position)
	- `dw` - delete a word (from cursor position)
	- `dd` - delete a line (from cursor position)
	- `D` - Delete from the current position to end of line (Delete remaining text on line)

- Replacing/Changing text:
	- `r` - replace the current character
	- `cw` - change the current word
	- `cc` - change the current line
	- `c$` (or) `C` - change text from current position to the end of the line($)
	- `~` - reverses the case of the character(upper <=> lower)

NOTE: We can repeat a command by preceding it with a number. Ex:
- `5k` => Move up 5 lines
- `80i<text><ESC>` => Insert entered text 80 times at cursor position

- Copying and Pasting:
	- `yy` - yank(copy) the current line
	- `y<position>` - Yank the position
	- `p` - paste the most recently deleted or yanked(copied) text.

7. Undoing and redoing:
	- `u` - Undo
	- `<CTRL-R>` - Redo

8. Searching:
	- `/<pattern>` - Forward Search(First match to Last match)
	- `?<pattern>` - Reverse Search(Last match to First match)
	- `n` - go to Next match
	- `N` - go to Previous match

8. `vi` Modes (How to get into them):
	- `<ESC>` - Normal Mode
	- `i`, `a`, `o`,.. etc - Insert Mode
	- `:` - Line Mode

Need vim help? Type `vimtutor` and hit enter at the command prompt.

### emacs editor

**`emacs`**

Also a powerful editor. Some people use vi, some use emacs. => Choose whatever you're comfortable with.

Opening a file: `emacs [file]` (edit file)

Emac command guide:
- `C-<char>` : means hold down CTRL while pressing character
- `M-<char>` : means hold down either ALT while pressing character (or) means press ESC key, release it, and then type a character.

- `C-h` : Help
- `C-x C-c` : Exit
- `C-x C-s` : Save the file
- `C-h t` : Built-in tutorial
- `C-h k <key>` : Describe the key
- `C-p` : Previous line
- `C-n` : Next line
- `C-b` : Backward one character
- `C-f` : Forward one character
- `M-f` : Forward one word
- `M-b` : Backward one word
- `C-a` : Go to beginning of the line
- `C-e` : Go to end of the line
- `M-<` : Go to beginning of the file
- `M->` : Go to end of the file
- `C-d` : Delete a character
- `M-d` : Delete a word
- `C-k` : Kill(cut)
- `C-y` : Yank(paste)
- `C-x` u : undo
- `C-u N <command>` : Repeat Command N times

### Graphical Editors

Some of the graphical editors are:
1. emacs - emacs has a graphical mode too
2. gedit - The default text editor for GNOME Desktop environment (Simialr to notepad)
3. gvim - The graphical version of vim
4. kedit - The default text editor for the KDE Desktop environment (Similar to gedit)

Note: Microsoft Office alternatives:
1. AbiWord - Microsoft Word Alternative
2. LibreOffice - Full Office Suite (Just like Microsoft Office)
3. Kate | Genie | jEdit | Sublime Text - Source Code Editors

## Delete Copy Move and Rename files

**Delete | Copy | Move | Rename**

- `rm` command: (remove)
	- `rm file` => Remove file
	- `rm -r dir` => Remove directory and its contents recursively
	- `rm -f file` => Force removal and never prompt for confirmation

- `cp` command: (copy)
	- `cp source_file destination_file` => Copy source file to destination file
	- `cp source_file1 [... source_fileN] destination_dir` => Copy source file to destination directory
	- `cp -i` => Interactive mode
	- `cp -r source_directory destination_directory` => Copy source directory recursively to the destination

If destination directory does NOT exist, it gets created with the contents of the source directory.

- `mv` command: (Move or Rename) 
	- `mv source [..sourceN] destination` => Moves source file(s) and/or Directories to Destination directory.
	- `mv -i source destination` => Interactive mode.

`mv` DOES NOT require `-R` to move Source Directories into Destination Directory

Ex: `mv subdir1 /subdir2/newFolder` => Moves subdir1 folder to /subdir2/newFolder folder

`mv file1 file2` => Rename file1 to file2 (Overwrites file2 if it exists) [file1, file2 in same folder]
`mv -i file1 file2` => Rename file1 to file2 (Asks to overwrite file2 if it exists) [file1, file2 in same folder]

## sort command

**`sort`**

`sort` sorts the text in a text file Alphabetically (by default) line by line.

Syntax: `sort file` (THE ORIGINAL FILE IS UNAFFECTED - THIS IS ONLY FOR PRINTING TO SCREEN/STDOUT)

Options:
- `-kF` => Sort by key supplied. F is the field number(column number) (Ex: `sort -k2 file.txt` => Sorts lines alphabetically according to the 2nd column on each line)
- `-r` => Sort in reverse order. Reverse alphabetical order by default.
- `u` => Sort Unique (Removes the duplicate lines)


## Create a collection of a group of files

**(bundle/archive)**

Use `tar`: `tar [-] c|x|t f tarfile [pattern]`

Simpler way to remember: `tar options tarFileName filesToBeArchived`

`tar` does NOT need the hyphen (-) for options, but including it is optional (no harm!). Create, extract or list contents of a tar archive using pattern, if supplied.

`tar` options:
- `c` => Create a tar archive
- `x` => Extract files from the archive
- `t` => Display table of contents (List)
- `v` => Be Verbose
- `z` => Use compression
- `f` file => Use this file

Usage examples:
- `tar cf tps.tar tpsreports` => create(c) an archive (tps.tar) for this file(f) called 'tpsreports'
- `tar xf tps.tar` => Extract(x) this file(f) 'tps.tar'
- `tar xfv taps.tar` => Be verbose(give a listing of all the extracted files)

## Compress Files

`gzip` command. (Compresses supplied file)

- `gzip file` => Compress files and adds extension '.gz' to it (original file AFFECTED!)
- `gunzip` => Uncompress files

Viewing contents of a gzipped file:
- `gzcat` => Concatenates compressed files
(OR)
- `zcat` => Concantenates commpressed files

### Disk Usage Stats
- `du` => Estimates file usage(Bytes)
- `du -k` => Displays sizes in KiloBytes(KB)
- `du -h` => Display sizes in human-readable format(Ex: 5M for 5 megabytes)

Combining `du` & `gzip`. Examples:
- `du -k data.txt` => gives how much space data.txt is using.
- `gzip data.txt` => compresses data.txt to data.txt.gz
- `du -k data.txt.gz` => gives how much space data.txt.gz (the compressed file) is using.
- `gunzip data.txt.gz` => uncompresses data.txt.gz to data.txt (original state)

### tar and gzip

**`tar`**
**`gzip`**

- `-z` option of tar uses gzip for compression while archiving. (Uses '.tgz' or 'tar.gz' extension)

Ex:
- `tar zcf tps.tgz tpsreports` => Compresses(z) and archives(c) this file(f) tpsreports into tps.tgz.
- `tar ztvf tps.tgz` => Displays contents(t) of compressed(z) archive file(f) tps.tgz in a verbose(v) way.

## WildCards

(Already done in other courses, just SKIPPING them here)
(Learn from notes of other, previous courses)

## Input Output and Redirection

There are 3 different types of input and output: 
- Standard Input => stdin => 0 (File Descriptor)
- Standard Output => stdout => 1 (File Descriptor)
- Standard Error => stderr => 2 (File Descriptor)

File Descriptor number is like the number/id of the inputs or outputs. The machine uses the numbers instead of 'standard input' (human readable form) to recognize input and output

### Redirection
- `>` => Redirects standard output to a file. (Overwries(truncates) existing contents)
- `>>` => Redirects standard output to a file. (Appends to any existing contents)
- `<` => Redirects input from a file to a command.

Ex:
- `echo new line > file.txt` => 'file.txt' contains the output of `echo` command ('new line').
- `ls -l > file.txt` => 'file.txt' contains the output of `ls -l` command (nothing printed on screen).
- `ls -l >> file.txt` => Appends the output of `ls -l` command to 'file.txt' (nothing printed on screen).

Ex:
- `sort < files.txt` => sort works on input which is the content of 'file.txt' (In sort's case it is the same as 'sort file.txt')

Note: Using file descriptors to work with stdin/stdout/stderr:
- `&` => Used with redirection to signal that a file descriptor is being used.

Ex:
- `2>&1` : Redirecting standard error to standard output (Combines standard error and standard output)
- `2>file` : Redirect standard error to a file.

### The Null Device
If you want to 'IGNORE/DISCARD' the output, you can send it to the Null Device('/dev/null'): Ex:
- `ls here not-here 2> /dev/null` [Don't want to see errors on screen nor save them to a file]

Null device is also known as the 'bit bucket'

Choosing whether to redirect standard output or standard error to a file. Ex:
- `ls -l 2> file.txt` => Redirects std error to 'file.txt'(No space between 2 and >)[& stdout to screen]
- `ls -l 1> file.txt` => Redirects std output to 'file.txt'(No space between 1 and >)[& stderr to screen]

Sending standard output to one file and standard error to another(or to the same). Ex: 
- `ls existingFile not-here-file 1> out.txt 2> err.txt` => Std. output (for existingFile) goes to out.txt and Std error (for not-here-file) goes to err.txt

Combining standard output and standard error (redirect to the same file): Ex: 
- `ls existingFile not-here-file > out.txt 2>&1`

The above appends standard error to standard output, so both are saved into out.txt only (not screen)

Ex: 
- `ls here not-here > /dev/null 2>&1` => Appends standard error to standard output, so both are sent to /dev/null (ignored)

Important: When NO file descriptor is used in redirection, Only the standard output is redirected but the standard input is printed on the screen. Ex: 
- `ls -l existingFile not-here-file > lsOutput.txt` = The stdout is saved in lsOutput.txt (not printed) while stderr for 'not-here-file' was not redirected and hence, was printed to the screen. 

Sample Output: 
- `ls cannot access not-here: No such file or directory` (but ls of existingFile was saved as content of lsOutput.txt)

### Combining input and output redirection

Syntax: `command < ipFileName > opFileName`

The command is run with 'ipFileName' as input and the output of the command is saved to 'opFileName'

Ex: `sort < file1 > file2`

## Comparing two files

- `diff file1 file2` = Compare two files.
- `sdiff file1 file2` = Compare two files Side-by-Side (file1 : left, file2 : right).
- `vimdiff file1 file2` = Highlight differences in vim editor.

### diff Example

**`diff`**

- `diff file1 file2`

Output: 
```
3c3
< this is a line in a file
---
> this is a line in a file
```

Here, 3c3 is following the pattern => `<LineNumeFile1><Action><LineNumFile2>`. `<action>` can be Add(a), changes(c) or Delete(d) indicating the kind of difference.
- `<` => @beginning of a line indicates it is a line from file1
- `>` => @beginning of a line indicates it is a line from file2
- `---` => It is just a separator

### sdiff Example

**`sdiff`**

`sdiff file1 file2`
Output:
```
line in file 1 | line in file 2
		> line in a file 2 
```
- `|` => Indicates differing lines (side-by-side lines separated by '|')
- `<` => @beginning of a line indicates it is a line from file1 (line only exists in file1)
- `>` => @beginning of a line indicates it is a line from file2 (line only exists in file1)

### vimdiff Example

**`vimdiff`**

`vimdiff file1 file2` (Both files will be opened in separate windows!)

- `<Ctrl-w> w` 	: Go to the next window
- `:q` 		: Quit (Close current window)
- `:qa` 	: Quit All (Close both files)
- `:qa!`	: Force Quit All (Force close both files!) - changes that you don't want to save.

## Searching in files and using pipes

Use the `grep` command to search inside files. `grep` displays Lines of a file matching a pattern.
(If we DON'T supply a file name grep uses the STANDARD INPUT to search against.)

Syntax: `grep pattern file`

Options:
- `-i` => Perform a search, ignoring case
- `-c` => Count the number of occurrences of the pattern in a file
- `-n` => Precede output with Line Numbers
- `-v` => Invert Match. Print lines that do NOT match.

Ex:
- `grep o secret.txt` => searches for 'o' in 'secret.txt' and prints the matching lines 
(lines from the file that contain 'o')
- `grep -v user secret.txt` => Matches all lines that do NOT contain 'user' in 'secret.txt' file.
- `grep -i User secret.txt` => Matches all lines that contain 'user' in 'secret.txt' file.(IGNORES CASE)
- `grep -n blah secret.txt` => Matches all lines that contain 'blah' in 'secret.txt' file.(PRINTS LINE NUM)

### Finding out the type of a file

The `file` command is used.

Syntax: `file file_name` => Displays the file type.

Ex:
- `file sales.data` (Ex. O/P: 'sales.data: ASCII text')
- `file jason.tar` (Ex. O/P: 'jason.tar: POSIX tar archive')
- `file collection` (Ex: O/P: 'collection: directory')

### Searching for strings in a binary file

To display printable strings contained in a binary file, use the `string` command.

Syntax: `string binaryFileName`

### Pipes or Pipelining

The pipe symbol is '|'. It's used to chain commands together.

Visualization: 'command-output | command-input'

(The pipe takes the std. output of one command(left) and feeds it as std. input to other command(right))

Only the standard output is sent as standard input to the next command. (use 2>&1 to send standard error as well - check redirection topic)

Common usage examples:
- `grep pattern file` <=> `cat file | grep pattern` (Equivalent)
- `ls -l | cat | grep -i john` (We can chain as many commands as we want)

### `cut` command

**`cut`**

- `cut [file]` => Cuts out selected portions of the file. (If file is omitted, uses STANDARD INPUT). (Cut does NOT affect the original file.)

- `cut -d<delimiter>` => Use delimiter as the field(column) separator
- `cut -fN` => Display the Nth field.

Ex: 
- `cut -d' ' -f2 file1.txt` => Selects column 2 from file1.txt using space as delimiter between fields
- `grep bob /etc/passwd | cut -d: -f1,5` => cuts 1 and 5 ':' separated columns of /etc/passwd. 

`/etc/passwd` contains user data such as name, home folder, etc.

### Translating Characters

**`tr`**

`tr` is used to translate all occurrences of a value/string in a file to another value/string. If NO file is supplied, it takes the STANDARD INPUT. Original file not affected.

Syntax: `tr "<oldchar>" "<newchar>" file`

Ex:
- `tr ":" " " file.txt` => Translate all the ':' with spaces(' ') in 'file.txt'.

### Formatting output into columns

**`column`**

Syntax: `column [options] [file...]`

Ex:
- `column -t` : Determine the number of columns the input contains and create a table. (**Space** is the delimiter between columns by default)

### more and less commands

**(Printing out to a pager)**

Already learnt. (Refer earlier or previous notes) Keep in mind that these two commands can also take take redirected inputs as well (STANDARD INPUT).
Ex:
- `cat /etc/passwd | less`

(THERE ARE MANY SMALL COMMANDS THAT DO ONE THING VERY WELL. WE CAN CHAIN MANY OF THESE COMMANDS TOGETHER TO EXECUTE SOMETHING COMPLEX AND POWERFUL)


## Copying files over the network

To copy files between 'remote server and local host' (or) 'between two remote servers'.

- SCP - SECURE COPY.
- SFTP - SSH(or SECURE) FILE TRANSFER PROTOCOL.

Both SCP and SFTP are extensions of the 'SSH' (Secure Shell) Protocol.
- (In SCP, we need to know what files are to be transferred while writing the command/connecting.)
- (In SFTP, we need NOT know before connecting, what files are going to be transferred.)

Using SCP/SFTP:
- Mac & Linux come with scp and sftp command line utilities (openSSH in the case of MAC)
- For Windows systems, we need to install a tool called 'putty' ['pscp.exe' and 'psftp.exe'].

Graphical SCP/SFTP clients:
1. Cyberduck, (Mac and Windows)
2. FileZilla, (Mac, Linux and Windows)
3. WinSCP. (Only Windows)

### SCP
- `scp source destination` => Copy source to destination (Destination is like - 'serverName:directoryPath')

(Full Syntax: `scp source_file_name username@destination_host:destination_folder`)

Ex:
- `scp sourceFileName host:destinationPath`,
- `scp z.txt linuxsvr:/tmp/`,
- `scp z.txt adminuser@linuxsvr:~/` => Transfer files as a different user(adminuser) [password required]

(We can use SSH or SFTP to check if the copied local files exist on the remote server now.)

SCP Options: 
- `-v` => We can use the `-v` parameter to print debug information into the screen.
- `-p` => An estimated time and the connection speed will appear on the screen.
- `-r` => Copy directories and their contents recursively.
- `-C` => The `-C` parameter will compress your files on the go, making the transfer faster. (No further compression if file is already compressed. Ex: .zip, .rar, .iso, ... etc)
- `-p` => Specify the Specific port to use. Ex: `scp -P 2249 Label.pdf mrarianto@202.x.x.x:.` (we are using port 2249)

By default SCP using `AES-128` to encrypt files. If you want to change to another cipher to encrypt it, you can use `-c` parameter. Take a look of this command. Ex:
- `scp -c 3des Label.pdf mrarianto@202.x.x.x:.`

The above command uses 3des algorithm to encrypt the file.

Limiting Bandwidth:
- `-l` =>  limit the bandwidth to use. (It will be useful if you do an automation script to copy a lot of file, but you don’t want the bandwidth is drained by the SCP process.) Ex:
	- `scp -l 400 Label.pdf mrarianto@202.x.x.x:.`
	
The 400 value behind “-l” parameter is mean that we limit the bandwidth for SCP process only 50 KB/sec. 
One thing to remember that bandwidth is specified in Kilobits/sec (kbps). It is mean that 8 bits equal with 1 byte. BUT, While SCP counts in KiloByte/sec (KB/s). So if you want to limit your bandwidth for SCP maximum only 50 KB/s, you need to set it into 50 x 8 = 400.

### SFTP:

`sftp user@host` => Start a secure file transfer session with host (host can be an IP address as well)
Ex:
- `sftp jason@host` (or) 
- `sftp tecmint@27.48.137.6` ... etc.

(NOTE: you maybe prompted for a password.)

SFTP Note/Points:
- Once you successfully connect, you are at the command prompt of the remote server.
- For example, `pwd` returns CWD on the server, `ls` returns `ls` of CWD on the server.
- To use the commands for your local host computer while connected, precede commands with an 'l',(stands for 'local'). 
- So, to view the CWD on your local system, type `lpwd`, to list the files in the CWD of your local system, type 'lls', .. and so on.

Therefore: SFTP commands:
1. `pwd` => Remote's Working Directory.
2. `lpwd` => Local System's Working Directory.
3. `ls` => List files on Remote.
4. `lls` => List files on the Local System.
5. `put localFile` => Puts a local system file onto the remote systems CWD.
6. `mput localFile1 [...localFileN]` => Put multiple Local System files onto the REMOTE.
7. `get remoteFile [localFileName]` => Get Remote file onto the Local system .
8. `mget remoteFile1 [...remoteFileN] [localFileName]` => Get multiple Remote files onto the Local system.

[NOTE: To transfer directories in `put`, `mput`, `get` or `mget`, user `-r` option (recursive)]

9. `?` (or) `help` => SFTP help command screen shows the commands we can use to accomplish various tasks.
10. `cd` => Changes directory on the Remote Server.
11. `lcd` => Changes directory on the Local System.
12. `mkdir` => Make a directory on the Remote Server.
13. `lmkdir` => Make a directory on the Local System.
14. `rm` => Remove files and Directories on the Remote Server.
15. `rmdir` => Remove empty Directories from the Remote Server.
16. `exit` or `bye` => Close/Terminate the SFTP the session.
17. `chown`, `chgrp`, `chmod` => All on the Remote Server.(NO command from SFTP to change local permissions!)
18. `lumask` => This is the only permission related command in SFTP for the Local System.

(Other utilities):
- The `ftp` command. (Don't use if possible, use SFTP or SCP.)
- `ftp host` => Start a file transfer session with host. (Not secured!)

Using `ftp` means that your Login credentials are sent in plain text over the network. The files that you download/upload are NOT encrypted either.

## Customizing the Shell Prompt

An Environment Variable holds the shell prompt.
- `$PS1` => for bash, ksh and sh.
- `$prompt` => Csh, tcsh, and zsh.

(Check `man bash` pages for complete info.)

**Bash Prompt:**

Format Strings: (That can be placed within the prompt environment variable):
- `\d` => Date in 'Weekday Month Day' format (Ex: Tue May 26)
- `\h` => Hostname (upto the first period (.))
- `\H` => Hostname
- `\n` => Newline
- `\t` => Current time in 24 hrs format (HH:MM:SS)
- `\T` => Current time in 12 hrs format (HH:MM:SS)
- `\@` (or) `\&` => Current time in 12 hrs am/pm format
- `\A` => Current time in 24 hrs HH:MM format
- `\u` => Username of the current user
- `\w` => Current Working Directory
- `\W` => Basename of the Current Working Directory
- `\$` => If the effective UID is 0, a '#', otherwise a '$'[Superuser(Eff.UID=0) gets '#', everyone else: '$']

Persist the PS1 changes(for subsequent sessions):
- PS1 changes created on the prompt are gone after we quit the session.(Not available for the next session).
- So, We must add the PS1 changes as a line to the '~/.bash_profile' file.

We can do this either 
1. Manually: Insert something like `export PS1="[\u@\h \w]\$"` into '~/.bash_profile' file.
(OR)
2. Append to the file: Like => `echo 'export PS1="[\u@\h \w]\$"' >> ~/.bash_profile`.

(NOTE: personal initialization files, like .bash_profile, are also known as 'Dot Files' since they begin with a '.')

## Shell aliases

Used for shortening long commands.
- `alias name=value` => Create a new alias(name) for a command/sequence of commands(;, &, || separated)(value)
- `alias` => List all of the current aliases that are set.

- Aliases can also be used for adjusting commmon typing errors (ex: 'grpe' alias for 'grep')
- Aliases can also be used to make Linux behave like another OS (ex: 'cls' alias for 'clear')

Removing Aliases:
- `unalias name` => removes the alias with name 'name'
- `unalias -a` => Removes all the aliases

Persist the Aliases(for subsequent sessions):
- Aliases create on the prompt are gone after we quit the session.(Not available for the next session).
- So, We need to add the alias command as a line to the '~/.bash_profile' file (just like for shell prompt).

This can be done:
1. Manually: Insert something like `alias cls="clear"` into '~/.bash_profile' file.
(OR)
2. Append to file: `echo 'alias cls="clear"' >> ~/.bash_profile`.

(NOTE: Keep your alias usage to a minimum. Because, working on a different system where your aliases don't work might cripple you/slow you down/Need to copy your configuration file to each system you work on)

## Environment variables

These are 'name=value' pairs. Usually, Environment variables are in UPPERCASE(convention). Ex: `EDITOR=nano`

(Use the `man bash` pages for more info on environment variables)

### Viewing all the environment variables

(And their values on the command line)

- `printenv` => Prints all the Environment variables to the screen.
- `printenv ENV_VAR` => Prints the value of the specified Environment Variable. (Case-Sensitive!)
- `echo $ENV_VAR` => Prints the value of specified Environment Variable. (prepend name with a $).

### Creating or modifying environment variables

Syntax: `export VAR="value"`

Ex:
- `export EDITOR="vi"` => Creates EDITOR environment variables to 'vi'.(or modifies value to it, if EV exists)
- `export TZ="US/Pacific"` => Sets the Default Time Zone to the US Pacific time.
(Date command would return a different date/time depending on the TZ environment variable value)

### Removing environment variables

Syntax: `unset VAR`

Ex:
- `unset TZ` => removes the Time Zone Environment Variable.

### Persisting the environment variables settings

The act of setting/unsetting the Environment Variables on the command line is NOT persistent. (That is, the changes made to them won't be available for the subsequent sessions). So, we must save the environment variables into the '~/.bash_profile' file.

This is done either:
1. Manually: Insert something like `export TZ="US/Central"` into '~/.bash_profile' file.
(OR)
2. Append to file: `echo 'export TZ="US/Central"' >> ~/.bash_profile`.

NOTE: Changing time-zone Environment Variable(TZ) to Indian Standard time: `export TZ="Asia/Calcutta"` => Now \t, \@, etc in the chell prompt will show IST. (Even the `date` command will show the IST only.)

**Important**
NOTE:
- Whenever the output of a command is too much/too long, we can pipe the output of that command to a pager utility like 'less' or 'more': Ex:
	- `cat bigBigFile.txt | less`

- Refreshing the terminal to include the changes made to '~/.bash_profile': To see the changes take effect, run:
	- `source ~/.bash_profile` (or) `. ~/.bash_profile` and the terminal is refreshed with the new changes.

(This is a handy command that can be used instead of exiting and restarting the terminal)

- To view users on the system, run:
	- `who`

- To view which user you are on the system(current user), run:
	- `whoami`

## Processes and job control

Creating and viewing processs, background vs foreground processes, killing a process, etc.

### Displaying process information

- `ps` => Display Process Status.(No arguments? Displays ps for all processes associated with current session)

#### Options for ps

**`ps`**

- `-e` => Everything, all processes(NOT just limited to your session).
- `-f` => Full format listing.
- `-u username` => Display username's processes only. (Ex: `ps -fu joehenderson`)
- `-p pid` => Display information for process with PID 'pid'.

The full listing `-f` contains: 
1. UID (User ID), 
2. PID (Process ID),
3. PPID (Parent Process ID),
4. Time , 5. Process/Command Name ... etc


One of the main reasons for running `ps` is to get the Process ID (PID)

NOTE:: PID != JOB NUMBER

Common `ps` commands:
- `ps -e` => Display all processes.
- `ps -ef` => Display all processes, full listing.
- `ps -eH` => Display a process tree. (IMPORTANT)
- `ps -e --forest` => Display a process tree. (IMPORTANT)
- `ps -u username` => Display user's processes.

Other common commands:
- `pstree` => Display processes in tree format.
- `top` => Interactive process viewer. (Press 'q' to exit, '?' for help)
- `htop` => Interactive process viewer. (Less popular, may not be available by default on the system)

The `top` command places the processes using most of the CPU and Memory resources at the TOP of the list.
It also displays the CPU and Memory usage columns.

#### Killing a currently running foreground process

- Press `<CTRL-C>` on the CLI while the process is running. (Pressing this kills the foreground process and return the shell prompt to the user)

#### Suspend a foreground process

- Press `<CTRL-Z>` to suspend a foreground process.

Note: A process that is suspended is NOT running in the background! It is actually stopped. A (stopped) process can be then run in the background : type `fg %jobnumber`

#### Background processes

It maybe convenient to keep a long running process in the background. Background processes do NOT block the execution of other processes (esp. on the CLI). 

##### Starting a background process

- `<command> &` => Start the command in the background. (It Displays two numbers as output => 'Job No.' in brackets[] and 'PID' (Ex: [1] 2373) ) Ex:
	- `./some-long-running-script &` => Starts the script in the background (Ex. O/P: [1] [4232]) (We can view the status of the process by running `ps -p 4232`)

### Listing jobs

**(Helps list all the currently active jobs => Usually lists the Background Processes)**

We can list all the currently running jobs in the system.
- `jobs [%num]` => List jobs. (No arguments? List all the active jobs)
- `jobs -l [%num]` => Gives a long listing of the jobs.

(The '+' sign in the jobs output represents the current job. The '-' sign in the jobs output represents the previous job.)

- `jobs %+` (or) `jobs %%`=> Refers/lists the current job.
- `jobs %-` => Refers/lists the previous job.

### Forcing processes into the background

- `bg` => Send a suspended process(current job) to the background.  (current job - refers to last job that was stopped in the FG or the last job that was started in the BG)
- `bg %num` => You can background a process with a specific job number 'num' by preceding it with a '%' sign. Ex:
	- `bg %1` => Forces a suspened process in Foreground to the Background (runs it in the background).

Forcing processes into Foreground:

- `fg`= Send a background process(current job) to the foreground. (Current job - refers to last job that was stopped in the FG or the last job that was started in the BG)
- `fg %num` (or) `%num` => Foreground a BG process with a specific jobno. 'num' by preceding it with '%' sign. Ex:
	- `fg %1` (or) `%1` => Forces a Background process into the Foreground.

## Killing Processes

**(Job-wise/Process-wise)**

### Killing any process using PID

- `<CTRL-C>` => Kills the foreground process.
- `kill pid` => Kill a process with Process ID 'pid'. (Default signal used by kill = TERM (termination) | 15)
- `kill -sig pid` => Send a signal 'sig' to a process (to kill a process).

NOTE: `kill -l` => Displays a list of signals. Ex:
- `kill 123` => kill process with ID 123. (Default signal used by kill = TERM (termination) | 15)

### Killing any process using job number:

-`kill %jobnumber` => Kills a process with job number 'jobnumber'. Ex:
	- `kill %1` => Kills process with job number 1.

### Signals have numbers associated with them

- `kill -l` => Displays a list of signals that can be sent to a process and the numbers associated with them.

For Example:
- TERM <=> 15 (Terminate signal)
- SIGKILL <=> 9 (KILL signal) .. etc.

Ex:
- `kill -15 123` => Same as kill process with ID 123 since default signal is -TERM (or -15)
- `kill -TERM 123` => Same as kill process with ID 123 since default signal is -TERM (or -15)

NOTE::
`kill -9 123` => If a process does NOT terminate with default signal '15' - then USE kill signal '9'.

### Summary

- To display information about all running processes = Use `ps` command
- To kill a process in the Foreground = Type `<CTRL-C>`
- To suspend a process in the Foreground = Type `<CTRL-Z>`
- To background a suspended process = Use `bg` command
- To foreground a process = Use `fg` command
- To display information about your running jobs = Use `jobs` command
- To kill jobs using the job number/Kill processes using the PID = Use `kill` command

## Scheduling repeated jobs with cron

**`cron`**

We can use cron to SCHEDULE and AUTOMATE tasks. The cron service STARTS when the SYSTEM BOOTS and checks for SCHEDULED JOBS to be RUN EVERY MINUTE.

- `cron` => A time based job-scheduling service.
- `crontab` => A program to create, read, update and delete your job schedules

`crontab` format: (config file that contains information about scheduled jobs)

Each Line in a cron table represents a 'job' and contains 2 parameters:
1. When to run
2. What to run.

Format:
```
* * * * * command
| | | | |
| | | | + -- Day of the week (0-6) - Starting with 'sunday'(0)
| | | + ---- Month of the year (1-12)
| | + ------ Day of the month (1-31)
| + -------- Hour (0-23)
+ ---------- Minute (0-59)
```

Ex: `0 7 * * 1 /opt/sales/bin/weekly-report` => This script runs every Monday 07 Hrs (or 7:00 AM).

Note:: Asterisk (*) => Matches any/every time (or date).

### Redirecting the output of the cron jobs

Ex: `0 2 * * * /root/backupdb/ > /tmp/db.log 2>&1` => Backs up database at 2:00 (AM) every day.
(Here > is used to redirect the std. output to the /tmp/db.log file along with std. error (2>&1))

### Using multiple values

- Use commas(,) to represent multiple values (or)
- Use divider(/) to divide the total time frame for that column. (or)
- Use ranges(-) to specify a range for time / date.

Ex: Run every 30 minutes:
- `0,30 * * * * /opt/acme/bin/half-hour-check`

Another way to do the same thing: (Dividing the total minutes(60) by 2 => half hour)
- `*/2 * * * * /opt/acme/bin/half-hour-check` 

Run for the first 5 minutes of the hour:
- `0-4 * * * * /opt/acme/bin/first-five-mins`

Using keywords/Shortcuts in your crontabs:
- `@yearly` 	=> `0 0 1 1 *` (Run once a year on the 1st day of the 1st month) (day can be any weekday)
- `@annually` 	=> `0 0 1 1 *` (Run once a year on the 1st day of the 1st month) (day can  e any weekday)
- `@monthly` 	=> `0 0 1 * *` (Run once every month on the 1st day of the month) (day can be any weekday)
- `@weekly` 	=> `0 0 * * 0` (Run once every sunday on every month) (sunday can be any day)
- `@daily` 	=> `0 0 * * *` (Run once every day at 00:00 (12AM), every month, any weekday)
- `@midnight` 	=> `0 0 * * *` (Run once every day at 00:00 (12AM), every month, any weekday) (12AM = midnight)
- `@hourly` 	=> `0 * * * *` (Run once every hour at start of hour (0th minute), every day, month, any wkday)

Not all of these shortcuts might work on your linux distribution. (Use `man cron` to check)

### crontab command

**`crontab`**

- `crontab file` => INSTALL a new crontab from the contents of the file specified.
- `crontab -l` => LIST your cron jobs. (No cron jobs? -> Ex. o/p = 'no crontab for adminuser')
- `crontab -e` => EDIT your cron jobs. (Invokes the editor specified in the '$EDITOR' environment variable)
- `crontab -r` => REMOVE all of your cron jobs.

Ex:
- `vi my-cron-file` => Make a cron file.

(Ex. contents: `0 7 * * 1 /opt/bin/weekly` -> runs the weekly file every monday)

- `crontab my-cron-file` => Installs the 'my-cron-file' as a cron/scheduled job in th crontab.
- `crontab -l` => Lists our cron jobs (Ex. o/p in this case: '0 7 * * 1 /opt/bin/weekly')

Once a cron job has been added to the crontab it is run at scheduled times and specified file.

- `crontab -r` => Deletes/Removes all the cron jobs(In this case, 'my-cron-file')

Therefore, cron service runs scheduled jobs and these jobs can be manipulated using the `crontab` command.

## Switching users and running commands as others

**`su`**

Use `su` to switch users:

- `su` (or) `su root` => Become Superuser (The admin is usually the superuser of the system)
- `su username` => Switch to account having user name as 'username'.

Ex:
- `su` : switches to the root user (superuser)
- `su oracle` : Switches to the user named oracle

### Options for su

**`su`**

1. `-` => A hyphen is used to provide an environment similar to what the user would expect had he/she logged in directly. 

For example, we end up in the HOME directory of the switched-in user. We can check the environment variables set for the currently-switched-to user using '-'. Otherwise, we can ONLY see environment variables associated with the previous user's account

```
export TEST=1
su oracle
echo $TEST  # Returns 1 even if TEST was the environment variable of the previous user's session.
```
```
export TEST=1
su - oracle	# (Using '-' to set the environment similar to direct login to terminal of the switched user)
echo $TEST	# Returns nothing (Because $TEST was not set in this (switched) user's session)
```

2. `-c <command>` => Specify a command to be executed.

If command is more than one word in length, surround it with quotes('' or ""). Ex: `su -c "ls -l"`. Ex:
	- `su -c COMMAND anotherusername` : Runs COMMAND as anotherusername [DOES NOT SWITCH USER]
	- `su -c COMMAND - anotherusername` : Runs COMMAND as anotherusername (& has access to his/her environment variables). DOES NOT SWITCH USER.
	
NOTE:: Alternate way to execute commands as another user account is to use the `sudo` command (later)

### User identification commands

- `whoami` => To know the effective username. To know what user you are logged in as. Ex:
	- `whoami` => 'jason'
	- `su oracle`
	- `whoami` => 'oracle'

- `who` => Lists all the users currently logged onto the system.


### The sudo command

**`sudo`**

**Execute commands as another user - Important!**

- `sudo` stands for 'Super User do' and typically used to execute commands as another user, usually SUPERUSER. (That is, it allows us to execute commands with the security privileges of another user)

It is commonly used to install, start and stop applications that require the 'root' user privileges.

Note: On running `sudo`, you might be prompted for a password(once in a session), and you have to give the USER'S PASSWORD (& NOT the `root` password) - And if the user has root permissions, the sudo command is executed.

#### Executing commands with sudo

- `sudo -l` => List the available commands
- `sudo <command>` => Run command a root(as the superuser)
- `sudo -u root <command>` => Same as running command as root(as superuser)
- `sudo -u user <command>` => Run the command as user 'user' (`-u` is used to specify the user.)

#### Switching users by using sudo su

- `sudo su` => Switch to the superuser(root) account.
- `sudo su -` => Switch to the superuser(root) account with root's environment.
- `sudo su - username` => Switch to username's account with username's environment.

Alternatively:
- `sudo -s` => Starts a shell with root(superuser) account.
(or)
- `sudo -u root -s` => Starts a shell with root(superuser) account.
- `sudo -u user -s` => Starts a shell as 'user' (from the specified account).

Examples:
- `sudo /etc/init.d/oracle start` => Starts an application called 'oracle' as the root/superuser.
- `sudo -u bob /opt/bobapp/bin/start` => Starts bobapp as the user 'bob'.
- `sudo -s` => Uses `sudo` to switch to the root/superuser account.

### Modifying the sudo configuration

- `visudo` => Edit the '/etc/sudoers' file. (We need root access to execute `visudo`)

Therefore, switch to root and run `visudo` (OR) run `sudo visudo` from current account

The visudo file format: There are many lines of code in the visudo file but one common type of line encountered is - Syntax: 
- `user host=(users)[NOPASSWD:]commands`
	- user 	 : username of an account,
	- host 	 : system name/ host name,
	- NOPASSWD:: 'Optional' parameter suggesting that this user does NOT need a passwrod to run these commands.,
	- commands : Contains all the commands the user can run(Multiple commands are comma(,) separated)

Ex:
- `adminuser ALL=(ALL)NOPASSWD:ALL`,
- `jason linuxsvr=(root) /etc/init.d/oracle`

Note: If you ever forget to run a command with `sudo`, you can run the command again with:
- `sudo !!` => Basically, it runs the previous command

`!!` refers to the last command in the command history and runs that command with superuser/root permission.

Running a previous command with `sudo` provided the command starts with a particular string:
- `sudo !u` => Runs the most recently executed command in history that starts with 'u' from the root/superuser account.



Summary:
- To switch users => Use `su` command.
- To execute commands with superuser control => Use `sudo` command.

## Shell history

All executed commands are added to the shell history, which can be displayed and recalled. Shell history is stored in Memory and on Disk. Commands can be stored in one these files (depends on shell):
- `~/.bash_history`, (BASH SHELL)
- `~/.history`,
- `~/.histfile`

### Viewing history

**`history`**

- `history` => Displays the shell history (each line contains a command along with a serial/command number).

### Setting the size of the history

**(Number of commands saved)**

The HISTSIZE environment variable controls the number of commands in the history.(500 by default)
- `export HISTSIZE=1000` => Sets the history size to 1000. (Can place this line in '~/.bash_profile' to persist changes)

### Repeating commands from history

- `!N` => Repeat command on line number N (in `history`)
- `!!` => Repeat the previous command.
- `!string` => Repeat the MOST RECENT comman STARTING with 'string'. (Ex: `!gre` => maybe executes 'grep')

### Reuse or pull out the arguments from the previous command

- `!:N` => Pulls out Nth argument from the previous command. `:N` - Represents a word on the command line . 0 - command, 1 - first argument, ... etc. Ex:
- `head file1 file2 file3`
- `vi !:2` => Pulls out argument 2 from previous command (file2) and opens it in the `vi` Editor

Another example: 
- `echo !:2 !ch:2` => Pulls out 2nd argument to previous command and 2d argument to the most recently used command that started with `ch` (Maybe chown, chgrp, chmod, .. etc).

Shortcuts: 
- `!^` => pulls out FIRST argument to the previous command. (`!^` <=> `!:1`)
- `!$` => pulls out LAST argument to the previous command. (`!^` <=> `!:N` where N is the Nth among N args) 
- `!*` => Reuse ALL the arguments to the previous command in the current command. (Ex: `grep !*`)

Ex:
- `head file1 file2 file2`
- `vi !$` => pulls out file3 and opens it in `vi` Editor.


### Searching for commands

- `<CTRL-R>` => Reverse search the shell history. (Matches typed pattern with commands in history)
	- `<ENTER>` - Execute the command
	- `<ARROWS>` - Change the command
	- `<CTRL-G>` - Cancel the search

### Autocompletion

Use the `<TAB>` key to autocomplete:
1. File and Directory paths, Other paths
2. Environment Variables
3. Usernames(~) [Ex: `~ja<TAB>` => `~jason`]
4. Commands

## Installing & managing software

Typically, when we want to install a software we do so with a 'Package'. Package is a 'Collection of files'. It contains:
1. Data, and 
2. Metadata: Package Description, Version, & Dependencies.

### Package manager
- It is used to - Install, Upgrade or Remove packages.
- It manages dependencies. (Automatically installs any required dependencies)
- Keeps track of what is installed. (What files belong to what packages, versions, etc)


### The RPM format

**`RPM`**

The Red Hat Package Manager

For installing Software on RPM Distros: RedHat, CentOS, Fedora, Oracle Linux, Scientific Linux. The `yum` command is a package manager utility for the distros supporting RPM format:
- `yum search string` => Search for packages (online, included in the pkg mgr) matching the 'string'.
- `yum info [package]` => Display information.
- `yum install [-y] package` => Install Package.
- `yum remove package` => Remove Package.

**Installing or removing software requires Superuser or root privileges**

RPM commands: (An **alternative** command to the `yum` utility)
- `rpm -qa` => List all installed packages.
- `rpm -qf /path/to/file` => List the file's packages.
- `rpm -ql package` => List all the package's files.
- `rpm -ivh package.rpm` => Install package
- `rpm -e package` => Erase/uninstall package.

Options:
- `-i` : Install package,
- `-v` : Verbose,
- `h` : Print hash messages

Examples(yum):
- `yum search inkscape` => searches online for matching 'inkscape' packages (from mirrors)
- `yum info inkscape-docs.x84_64` => Gets info on a particular package (Ex: one of matched packages in search) (info gives a brief descrption and specs to help understand what the package is)

If installation/removal requires superuser access: (run `su -s` and switch or `sudo` the command)

- `sudo yum install inkscape` => Installs the 'inkscape' package (With prompt asking for yes(y)/no(n))
(OR)
- `sudo yum install -y inkscape` => Installs the 'inkscape' package (Without prompt)

- `sudo yum remove inkscape` => Removes the 'inkscape' package (With prompt asking for yes(y)/no(n))
(OR)
- `sudo yum remove inkscape` => Removes the 'inkscape' package (Without prompt)

### Installing packages not included in the package manager

These are the applications/software that are not `yum search`able. In that case, we must:
1. Goto the website and directly download the .rpm package file for the application(GOES TO '~/Downloads'),
2. Run the `rpm` commands to install (NOT the `yum` commands)
Ex:
- `rpm -ivh nautilus-dropbox.fedora-i386.rpm` => Installs the package (Provided it exists [Downloaded])

### General package info commands

**(Any installed package)**

- `rpm -qa | sort | less` => Displays all the installed package in alphabetical order on the `less` pager.
- `rpm -qf /usr/bin/which` => Displays to what package a file belongs to(Ex.o/p: `which-2.20-7.el7.x86_64`)
- `rpm -ql which` => Lists all the files that are part of the 'which' package

Note: 
1. While installing a package, it also installs All the Other Packages that this Package depends on.
2. Use the `which package-name` command to check if the package was installed(returns location of it)]

### Installing on Debian Distros with the APT package format

**`apt`**

The 'Debian' distros do NOT use '.rpm' packages but uses `.apt` instead. (Debian distros also includes 'Linux Mint' and 'Ubuntu')

Debian based systems use a package manager called `apt`:
- `apt` is composed of a few smaller utilities, two of the most famous of them being `apt-cache` and `apt-get`.

Commands:
- `apt-cache search string` => Searches for a package (online, included in the pkg mgr) matching the 'string'.
- `apt-get install [-y] package` => Installs the package. If `-y` is supplied, it does NOT prompt for a y/n.

- `apt-get remove package` => Remove a package from the system. (Leave any configuration files undeleted)
- `apt-get purge package` => Remove a package from the system and delete the configuration files also.

- `apt-cache show package` => Displays info about a package.

### The dpkg command used in addition to the `apt` utility

**`dpkg`**

Installing from '.deb' that was downloaded to the system - similar to directly installing `.rpm` pkgs.

- `dpkg -l` => List installed packages.
- `dpkg -S /path/to/file` => List the file's package. (Capital S option)
- `dpkg -L package` => List all the files in the package. (Capital L option)
- `dpkg -i package.deb` => Installs the package.

ONCE AGAIN, INSTALLING PACKAGES ON DEBIAN DISTROS ALSO REQUIRES `ROOT` ACCESS. `su` command to switch to root (or) `sudo` command to execute as 'root'.

Note: 
1. While installing a package, it also installs All the Other Packages that this Package depends on.
2. Use the `which package-name` command to check if the package was installed(returns location of it)]

## The Linux boot process

**Watch Udemy Course for full demo of the boot process**

### BIOS

- The BIOS stands for Basic Input-Output.
- It is a special firmware - that checks the hardware connected to a system.
- It is Operating System Independent (Applies to all OSes and not just Linux)
- Its primary purpose is to find and execute the 'Boot Loader'.
- BIOS - performs the POST (Power-On Self Test) which basically tests CPU, MEMORY, etc.
- Only if the POST succeeds does the BIOS load the 'Boot Loader'.

- BIOS - knows about different 'Boot devices' : Like the Hard Drives, USB Drives, DVD Drives, etc.
- The BIOS searches the above list for a 'bootable device' in the order specified.
- The boot device search order can be changed (Interrupt the boot sequence and enter into an interactive mode).
- The key sequence to do this (change boot device search order) varies from one hardware manufacturer to another.

(Ex: `F2` opens the setup in some systems. You might have to press `F12` and then enable `F2` key from the options.)

Once the 'Bootable Device' is found, the BIOS will run the 'Boot Loader'. This is typically the 'GRUB' (Grand Unified Bootloader) is used. But, on older Linux systems you may find 'LILO' (Linux Loader). The primary purpose of the 'Boot Loader' is to START the OPERATING SYSTEM. Boot loaders could start the Operating System with Different Options. (If there are multiple OSes installed, we can tell the Boot loader which OS to load/run.)

### Initial RAM Disk

- `initrd` or Initial RAM Disk is a temporary file system that is loaded from Disk and Stored in Memory. It contains helpers and kernel modules (sometimes called 'Drivers') required to load the permanent OS file system.

Once the real OS filesystem has been mounted by `initrd`, its job is done and the loading process continues from the real Operating System File System. 

### The boot directory

**`/boot`**

The '/boot' directory contains the files required to boot Linux:
1. initrd
2. kernel (The Linux Kernel)
3. Boot Loader Configuration

#### Viewing the boot directory

- `ls -F /boot` => Lists the directory with visual classification(-F)
	- The kernel is typically named 'vmlinux' or 'vmlinuz' (Name ends in 'z' if the kernel is compressed)
	- The Initial RAM Disk is 'initrd.img'

NOTE: You can use -F (in `ls` command) which classifies the file with different special character for different kind of files:
	- / – directory.
	- nothing – normal file.
	- @ – link file.
	- * – Executable file

### The kernel ring buffer

The ring buffer is a data structure maintained by the kernel to store messages from the kernel. It is of fixed size and older messages get deleted when new ones are added. Get kernel messages by executing the command:
- `dmesg` 
(or) 
- `dmesg -T` (Also displays the time of the message in human-readable format). The message log contains even the earliest messages that fly away quickly during boot process

#### Location of the kernel messages

- `var/log/dmesg` => (Viewing this file is equivalent to running the `dmesg` command) This files contains all kernel messages from start to now, unlike the ring buffer's `dmesg` command.

## Linux uses run Levels

**(To determine what processes and services to start)**

### Run levels

- 0 = Shuts down the system.
- 1, S, s = Single user mode. Used for maintenance.
- 2 = Multi-User mode with GUI(Debian/Ubuntu).
- 3 = Multi-User text mode(Red Hat/CentOS).
- 4 = Undefined.
- 5 = Multi-User with GUI(Red Hat/CentOS).
- 6 = Reboot.

### Setting the run level

Traditionally run levels were controlled by the 'init' program. The File containing 'init' configurations is: `/etc/inittab`.

To change the "Default" Run Level:
1. Open '/etc/inittab' file
2. Go to the 'initdefault' line and change the run level number. Ex: `id:3:initdefault:` line where 3 is the Default Run Level.

To Change run level: (`telinit`) (NOT the default run level)
- `telinit 5` => Changes run level to 5 [Multi-User with GUI]

NOTE: 'init' is slowly being phased out by other utilities like 'systemd'.

### systemd

**`systemd`**

Uses 'targets' instead of run levels. (targets are roughly equivalent to run levels). To get the list of available 'targets', look inside: '/lib/systemd/system' (Ex: `ls -l /lib/systemd/system`, `ls -l /lib/systemd/system/runlevel5.target`)

Run level targets are actually 'symlinks' to the real targets being used.

To get/view the System default run-level target:
- `systemctl get-default` => (Sample output: 'multi-user.target')

To change the "default" run level or target with systemd: Ex: 
- `systemctl set-default graphical.target` ('graphical.target' is equivalent to 'run-level 5' (Multi-User GUI))

To change the target/run level target: (NOT the default run level target)
- `systemctl isolate graphical.target` => Changes run level to 'graphical.target'.

## Rebooting

Even though we can use the:
- `telinit 6` (or)
- `systemctl isolate reboot.target` to reboot the system,
We can also use system command:
- `reboot` => Reboots the system.

- `Shutdown` command for rebooting:

Even though we can use: `telinit 0` to shutdown, there exists commands to shutdown the system:
- `shutdown [options] time [message]` 
	- `-r` option => Tells the system to reboot after shutdown!

'time' formats:
1. `HH:MM` = Shutdown at HH hrs and MM mins.
2. `+N` = Waits for N minutes before performing shutdown.
3. `now` = Shuts down immediately.

'message': This is a broadcast message sent to all users on the system that it is being shutdown/rebooted. (All logged-in users are notified that the system is going down, and login operations are blocked.)

Ex:
- `shutdown -r 15:30 "Rebooting!"`,
- `shutdown -r +5 "Rebooting soon!"`,
- `shutdown -r now`

Power Off a system: (3 main ways)
1. `telinit 0`
2. `systemctl isolate poweroff.target` (Selects the 'poweroff' target)
3. `poweroff` (Simple command that can be executed at the CLI to power off the system)

## The system log

Aids in the process of messages. (Each process need not have to create its own log files). Allows logging to be centrally controlled. Uses facilities and severities to categorize messages.

### Facilities

What type of program / what place in the system the message originated from.
```
0 	kern 		kernel messages
1 	user 		user-level messages
2 	mail 		mail system
3 	daemon 		system daemons
4 	auth 		security/authorization messages
5 	syslog 		messages generated by syslogd
6 	lpr 		line printer subsystem
7 	news 		network news subsystem
8 	uucp 		UUCP subsystem
9 	clock 		daemon
10 	authpriv 	security/authrization messages
11 	ftp 		File Transfer Protocol
...
15 	cron 		clock daemon
16 	local0		local use 0
16 	local1		local use 1
...
16 	local7		local use 7
```

We can use local0 to local7 for our own purposes.

### Severities

```
0 	Emergency	emerg(panic)	System is unusable
1 	Alert 		alert 			Take action immediately
2 	Critical	crit			Critical Conditions
3 	Error		err (error)		Error conditions
4 	Warning		warning (warn)	Warning conditions
5 	Notice		notice			Normal but significant condition
6 	Info		info			Informational messages
7 	Debug		debug			Debug-level messages
```

### rsyslog

**`rsyslog`**

`rsyslog` is one the syslog servers in use.

1. Main configuration file for `rsyslog`:  '/etc/rsyslog.conf'

2. Add additional configuration files: `IncludeConfig /etc/rsyslog.d/*.conf` => The `IncludeConfig` directive asks the rsyslog to add any file ending with '.conf' and existing in the '/etc/rsyslog.d/' directory.

Logging rules:
1. Selector field: Syntax: `FACILITY.SEVERITY`
	- '*' severity for all[Ex: 'mail.*' <=> 'mail'] (Wildcards supported for both facilities and severities),
	- 'none' severity for none[Ex: mail.none],
	- 'mail.emerg;ftp.err;cron.info' => Match multiple severities with semicolon(;)

2. Action Field: How a message is processed.

### Caching vs non-caching

Caching is used if the path starts with a hyphen(-) Ex: 'mail.*' logs saved to '-/var/log/mail.info'

You may lose some messages during a system crash if you are using the crash mode. Using caching mode can improve I/O performance.

Different severities can have different caching modes: Ex:
- `mail.info` ===> '-/var/log/mail.info'
- `mail.warn` ===> '-/var/log/mail.warn'
- `mail.err` ===> '/var/log/mail.err' (No caching)

Lower severities are cached while higher severities are not cached.

Generate 'syslog' messages: Use the `logger` command. Ex:
- `logger [options] message`.

Options for `logger`:
- `-p FACILITY.SEVERITY` => Defaults to 'user.notice' if nothing is specified.
- `-t TAG` => Tag our messages in the log file.

Ex:
- `logger -p mail.info -t mailtest "Test."`
- `sudo tail -1 /var/log/mail.log` => (Sample o/p: 'Apr 4 14:33:16 linuxsvr mailtest: Test.')

NOTE: `logrotate` command => Did not learn (go back to videos if you wish to learn)

NOTE: Removing blank lines and comment lines from a file/stdin:
- `grep -Ev '^#|^$' fileName`
	- The ^ stands for beginning of line in regular expression pattern. (^# => comments)
	- The $ stands for the end of the line in regular expression pattern. (^$ => Blank lines)
	- | stands for OR (this[left side] or that[right side])

## Disk management

Disks can be divided into parts - called Partitions. Partitions allow you to separate data. Participation Schemes: Ex: 
1. OS | Application | User | Swap,
2. OS | User Home Directories | Etc..

(As a system administrator, you get to decide)

### Advantages of partitioning

Can protect the overall system. Keep users from creating outages by using a home directory partition. (Ex: If the system runs a web server, we can partition OS and the server on the disk, so damage/outage in one won't affect the other, esp. the OS will still keep running)

### Master Boot Record

**(MBR)**

- MBR - It's a 'boot sector' that exists at the beginning of partitioned computer mass storage devices like fixed disks or removable drives.
- MBR = Boot Sector (sectors, tracks, cylinders ...) at the beginning of a storage device
- MBR contains information about how the 'logical partitions' are 'organized' on the disk. The information is contained in a Partition Table.
- MBR allows UPTO '4' PRIMARY partitions.

If you want to use more than 4, we need to use an 'Extended Partition'. An Extended Partition is a special kind of primary partition that is used as a 'container' for OTHER partitions. (Hence, create unlimited number of partitions inside the extended partition)

Disadvantage of MBR: Can ONLY address 2TB of disk space.

### GUID Partition Table

**(GPT)**

- It is slowly replacing MBR as the boot sector of the partitioned disks.
- GUID = Global Unique Identifier.
- GUID is actually part of UEFI(Unified Extensible Firmware Interface) that is gradually replacing BIOS
- GPT has been already used in some BIOS systems because of the MBR's disadvantage(support only 2tb space).
- GPT: NO Concept of Primary/Extended Partitions

GPT Supports:
- Upto 128 Partitions.
- Upto 9.4ZB Disk Sizes. (ZB = Zeta Byte)

(GPT NOT supported by older OSes and May require Newer or Special Tools)

### Mount points

A mount point is simply a DIRECTORY that is USED to ACCESS THE DATA on a Partition.

- '/' (slash) => It is always a Mount Point.(At least 1 Partition is mounted on the '/' directory). Any other additional partitions are mounted Inside the '/' Directory Tree.

Ex: If we allocated a partition to the '/home' directory (mounted), then all the files and directories inside it can be found under that partition. (Ex: '/home/jason' is on the partition mounted on '/home') 

If we, say, umounted (remove) the `/home` partition and instead allocate it to the '/export/home' direcory (mount) then all the files inside '/home' will be available under the mounted partition of '/export/home'. (Ex: '/export/home/jason' available under the mounted partition '/export/home')

### Mount partitions over existing data

We can mount partitions over existing data. For example, if files(or directories) were create inside '/home' before the '/home' partition was mounted/create, those files will NOT be accessible after '/home' is mounted as a partition. They will exist but you not be able to access them.

Ex: Assume '/home' is not mounted and '/' is the existing mount:
- `mkdir /home/sarah`
- `mount /dev/sdb2 /home` ('/home' mounted/partitioned)

You will not be able to access '/home/sarah' now. Data for that folder exists on '/' partition. Therefore, We cannot access the '/home/sarah' folder from the '/home' partition.

- `unmount /home` (Removing the '/home' partition, so files inside belong once again to '/' mount). You can now access '/home/sarah' once again since mount was '/' when 'sarah' directory was created

### Mount points over other mount points

This is possible. For Example: If '/home' is a mount point, we can create another mount point '/home/jason' over the existing '/home' mount point. (The important thing to note is that '/home' must be mounted BEFORE mounting '/home/jason'!).


### fdisk to create and modify partitions on a disk

**`fdisk`**

`fdisk` is a standard linux tool or a utility that has been traditionally used to CREATE and MODIFY PARTITONS on a Disk. (Alternatives: `gdisk` or `parted`)

Note:: Earlier version of `fdisk` are NOT supported by GPT.

To manage the partitions on a disk using the `fdisk` utility, simply provide the 'path' to the 'device' you wish to manage as an argument to the command, Ex:
- `fdisk /path/to/device`

- `fdisk -l` => Displays a list of available devices('disks') and all the 'partitions' they contain. You may like to use `fdisk -l | less`. (The above will list the disks and the partitions that they have, if any.)

- `fdisk -l /dev/sda` => Displays a specific disk device's partitions (and its nested partitions).

- `fdisk /dev/sdb` => Opens the command utility for '/dev/sdb' disk device (Use 'm' for commands help) (Once you run this command, the `fdisk` utility opens up, with its own commands:)

Commands inside `fdisk` device manager:
- p: print the partition table
- n: create a new partition
- d: delete a partition
- q: quit without saving changes
- w: write the new partition table and exit
- l: View a list of partitions along with their numbers

#### CREATE an MBR partition

**(Inside a disk using `fdisk` device manager)**

1. Press `n` to create a partition 

- Prompted to press 'p' for primary partition (or) 'e' for extended. (You chose 'p' - primary, say)
- It will ask you to choose partition number, 1 to 4. (Default is partition 1) (You chose 1, say)
- It will prompt you to select a start address from X-to-Y. (Default is X) (You chose X, say)
- It will ask you for the size of the partition. Format to enter: +NS (Ex: You typed '+1G', say)

(S is size = K for KiloBytes, M for MegaBytes, G for GigaBytes)
(N is the quanity. Ex: '+1G' means you chose 1 GigaByte of data from start address(X) for that partition)

- Partition is Created (Inside the selected disk device)

Example Output: 'Partition 1 of type Linux and of 1 GiB is set'

Once you create a partition 'x' (1 <= x <= 4), the next partition will ask you to select a partition number from '1-4 excluding x'. Suppose you selected 1 initially then next time it will ask you to select a partition number from 2-4.

The default size for any partition is the full remaining size that you have left. For example you may create 3 partitions of sizes 1GB, 2GB, and for the third one just hit `<enter>` and the default/remaining size is selected for it.

Note: Default partition type created is 'Linux' and represented by the number '83'.

2. CHANGE the partition TYPE:
- Type 't'
- Output is 'selected partition is 1'
- You are prompted for the Partition number(A hex number) [Says type 'L' for help with partition types]
- Type 'l' to see the list of partitions and their numbers.

(Say, Linux is 83 and you want to change to 'linux Swap' type, which is '82')

(Note: The numbers are in hexadecimal format, so even 'fe' is a number)

- You are prompted again for the Partition type Hex number. You Type '82' (say)
- Sample Output: `Changed type of partition 'Linux' to 'Linux Swap / Solaris'`

Note: You may repeat step (A) and, optionally step (B), for subsequent partitions you may want to create (and change the type of).

#### View all the existing partitions

**(Partition Table)**

- Type `p`.

#### DELETE a partition

**(Inside the chosen disk)**

- Type 'd'
- As we enter ‘d‘, it will prompt me to enter partition number that we want to delete from disk.(Ex: '4')
- It will delete that partition number (Ex: '4') on disk and shows free space in partition table. 

#### SAVING all the partitions added or deleted in the fdisk utility

**(Also EXITING/QUITTING)**

- Type `w` : It saves all the partitions it showed in the partition table (whatever we added/deleted) and quits the utility back to the command prompt.

#### QUITTING without Saving

- Type `q`.

#### CREATING a GPT Partition

**(Inside a Disk using the `fdisk` utility)**

1. Type 'g': (Prints message that you 'building a new GPT disklabel')
- Simialr commands to MBR. (n-create, p-print GPT table, d-delete partition, w-save&quit, q-quit)
- Only thing to remember is that instead of '1-4' partition numbers, there are '1-128'.
- No primary/extended partitions like in MBR. (All partitions are equival)

### File systems

Before a partition can be used by a system, it will need a File System.

- `ext` : Extendeded file system was create specifically for linux and is the default(ext2, ext3, ext4 are later releases)

- Other File Systems: 'ReiserFS', 'JFS', 'XFS', 'ZFS', 'Btrfs'

#### Create a file system

- `mkfs -t TYPE DEVICE` => Creates a file system of specified TYPE on the mentioned disk DEVICE. (DEVICE: path to the partition where you want the file system to reside). (Ex: `mkfs -t ext3 /dev/sdb2`)

Note: We may also use dot(.) notation instead of `-t`: Ex. `mkfs.ext4 /dev/sdb3`

Location of the mkfs files: `ls -l /sbin/mkfs*`

'mkfs' help: `man mkfs.ext2` to find more info about the ext2 file system creation commands.

### Mounting a device partition

**(Mount Point is simply a directory which we place a device partition on)**

(After creating and assigning a file system.)

- `mount DEVICE MOUNT_POINT` => Mounts a device partition to the directory specified.

Ex:
- `mount /dev/sdb3 /opt`

#### Viewing the currently mounted file systems

- `mount` => No Args - Therefore, mount displays all the filesystems (physical as well as virtual file systems.)

Manual mounts do NOT persist!:

In order to makes mounts persist between reboots, add an entry in the '/etc/fstab' file.

#### Unmount a file System

**(`umount` command)**

- `umount DEVICE_OR_MOUNT_POINT`

Ex:
- `umount /opt` (unmount using mount point)
- `umount /dev/sdb3` (unmount using device partition)

#### Preparing a swap space

Instead of creating a file system and mounting it, we can create a 'Swap Area' and 'Enable' it.
- `mkswap DEVICE` => Creates a swap space.(Ex: `mkswap /dev/sdb1`)
- `swapon DEVICE` => Enables the created swap space.(Ex: `swapon /dev/sdb1`)
- `swapon -s` => Displays the swap devices in use.

### The file system table

**`/etc/fstab`**

Controls what devices get mounted and where on boot. Each entry(one line) has 6 fields:
1. Device (label/path-to-device (or) UUID)
2. Mount point
3. File system type
4. Mount options (multiple options separated by a comma(,) but No spaces in between)
5. Dump Utility (Dump = 0 : Ignore FS, Dump = 1 : Backup the FS)
6. fsck order (file system check order - On boot) [0: skip FS check, 1: checked first, 2: checked next]
(Lines starting with '#' are comments and are ignored)

Example Entries: 
- `/dev/sda2		/		xfs 	defaults 	0	1`
- `/dev/sda1		swap 	swap 	defaults 	0	0`

Example using UUID:
- `UUID=dbae4fe7-b06f-4319-85dc-b93ba4a16b17		/		xfs 		defaults 	0	1`

You may ignore the dump utility column (leave it at 0) if you do not use it to backup filesystems.Good practice to set `fsck` of '/' to 1 and remaining FSes to '2'

- `man fstab` => Information about the full list of options.

#### Viewing labels and UUIDs of file systems

- `lsblk -f` => Shows label, name, fstype, and UUIDs of devices.
- `blkid` => 'Shows the path, type and UUIDs of devices'

#### Labelling a file system

**(Changing the name)**

For 'ext' filesystems we can use the `e2label`
- `e2label DEVICE MOUN_POINT` => Changes label of device(FS) at mount point(directory).

Ex:
- `e2label /dev/sdb3 opt`

## Managing users and groups

Linux is a multi-user OS. The multi-users can also use the system at the Same Time! Each user account has the follwoing fields associated:
1. Username (or Login ID)
2. UID (user ID). This is a unique number.
3. Default group (to which user belongs) (GID or group ID)
4. Comments
5. Home directory location
6. Shell (Shell to execute when user logs into the system)

All the user information(above) is stored in the - `/etc/passwd` file: Separated by a colon(:). The FIRST ENTRY in the file is the ROOT/SuperUser account. Format of each user's account(one entry = one line = one user):
- `username:password:UID:GID:comments:home_dir:shell`

### The root account

- `root:x:0:0:root:/root:/bin/bash` => (root user with x password, 0 uid, 0 gid, comment 'root', '/root' home dir, '/bin/bash' default shell to execute on login).

UID and GID for the root account are '0'.

Other user account example:
- `joe:x:1000:1000:Joe Henderson:/home/joe:/bin/bash`

NOTE!: password is 'x' - Exncrypted password is actually stored in the '/etx/shadow' file.

Note:
1. Better to have Usernames less than 8 characters or else[convention] we see + sign appended at 8th character position (or UID instead). Ex: Run this command for a long username: `ps -fu joehenderson`.
2. Usernames are case-sensitive. (All lowercase by convention).
3. Numbers are allowed in usernames.
4. Do Not use special characters.

### Passwords are stored in a shadow file

**'/etc/shadow'**

Encrypted passwords used to be(earlier) stored in 'etc/passwd'. But, '/etc/passwd' is readable by "everyone". Now(current linux), encrypted passwords are stored in '/etc/shadow'. '/etc/shadow' is readable by 'root'/'superuser' alone. This prevents users trying to crack passwords.

### UIDs

The root/superuser account always has `UID = 0`. UIDs are unique numbers. System accounts typically have UIDs less than 1000 (< 1000). (Configured in '/etc/login.defs')

### GIDs

The GID listed in the '/etc/passwd' file is the default group for an account. New files belong to a user's Default group.
Users can switch groups using the `newgrp` command. (This can be done before creating new files for the new group)

Note: Systems or applications also have accounts - viewable inside the '/etc/passwd' file.

### Comment field

- Typically contains the user's full name. 
- In the case of system or application accounts, it often contains what the account is used for.
- It may contain additional info, like phone number.
- Also called the GECOS field.

### Home directory

Upon login, the user is placed inside his HOME directory (Ex: '/home/jason' for user 'jason'). If this directory does NOT exist then he is placed in the root directory('/').

### Shell

The shell will be executed when a user logs in. List of available shells are in '/etc/shells'. The shell does NOT have to be a shell: 

Example: To prevent the interactive use of an account, use : '/usr/sbin/nologin' (or) '/bin/false' as the shell.
(In the above, No one can execute the shell interactively, but only execute a menu-driven application that only gives them access to certain actions). Shells can be command line applications.

### The /etc/shadow file

Contains the encrypted passwords of the user accounts.

Format:
`username:encryptedpass:dayssincepasswordchanged:numdaysbeforewhichpasswordmustbechanged:daystochangepass(99999-neverchange):daystowarnusertochangepass:numdaysafterpasswordexpiredtodisableacct:numdayssinceacctdisabled:futureuse`

Ex:
`root:$@234524#242Dde#$3:16502:0:99999:7:::`


### Creating a user account

**(Requires root account privileges - Ex> use 'sudo')**

Syntax: `useradd [options] username` 

Options:
- `-c "COMMENT"` => Comments for the account.
- `-m` => Create the home directory
- `-s /shell/path` => Path to the user's shell
- `-g GROUP` => Specify the default groud.
- `-G GROUP2,[...GROUPN]` => Additional groups(no spaces between commas)

Note:: Specify option `-u UID` to explicitly set the UID of the account being created. Ex: `-u 97`.

Ex:
- `useradd -c "Grant Stewart" -m -s /bin/bash grant`,
- `useradd -c "Eddie Harris" -m -s /bin/bash -g sales -G projectx harris` (Added to sales and projectX grps)

### Create a password for the created user

Syntax: `passwd username` 

Ex:
- `passwd grant` => System asks for password for the user 'grant' (and a retype to confirm).

Note: The created user entry and his password are "Appended" to the '/etc/passwd' and '/etc/shadow' files respectively.

### System or application accounts

Not every account is meant to be for a user. Some accounts exist to run applications or perform system functions. Examples of these accounts include those that run web server processes, database server processes, etc.

Extra Options:
- `-r` : Requests create an application/system account. (This means that the application receives a UID in the application UIDs range)(As defined in the '/etc/login.defs' file)
- `-d HOME_DIR` : Specify Home Directory using the `-d` option (instead of the `-m`) - we can give location. (Default home directory, if not specified in -d, is `/home/acctname`)

Ex:
- `useradd -c "Apache Web Server User" -d /opt/apache -r -s /usr/bin/nologin apache` (We do Not want someone to login to this system using the application account - hence => /usr/bin/nologin)

#### The -m option

**`-m`**

When using the `-m` option, the Home directory for the user is created. The contents of '/etc/skel' (stands for 'skeleton') are copied into the User's Home directory. This '/etc/skel' contains shell "configuration files" ('.profile', '.bashrc', etc)

### Deleting an account

Syntax: `userdel [-r] username`

Ex:
- `userdel grant` => Deletes user 'grant' from system but keeps his home folder un-deleted.
- `userdel -r grant` => Deletes user 'grant' from system and also deletes his home folder. (The `-r` also removes the user's mailspool file if it exists.)

### Mpdify an existing account

Syntax: `usermod [options] username`

Similar options to `useradd`:
- `-c "COMMENT"` => Comments for the account.
- `-s /shell/path` => Path to the user's shell
- `-g GROUP` => Specify the default groud.
- `-G GROUP2,[...GROUPN]` => Additional groups(no spaces between commas)

Ex:
- `usermod -c "MYSQL User" mysql` => Updates comment associated with a MySQL account.


### Group details and creation

The group details are stored in the '/etc/group' file.

Format of the entries in the file: `group_name:password:GID:account1,...,accountN`

(Here too, password is 'x').

GID is the group ID - A unique ID for the group.

FIRST entry in the '/etc/group' file is the 'Root Group'. Ex: `root:x:0:`

Other group example: `sales:x:1001:john,mary`

IMPORTANT NOTE: Users whose default is a certain group are NOT shown in the entry for that group in '/etc/group' file. 
BUT, we can check the '/etc/passwd' file to find the user's default group (or) run `groups user-name`.

### The /etc/gshadow file

**`/etc/gshadow`**

The encrypted group passwords(x) are stored in the '/etc/gshadow' file.

Groups that a member belongs to: `groups [USERNAME]`

Ex:
- `groups root` => Displays all groups that root belongs to.
- `groups` => Displays your(currently logged in user) groups (groups that you as the user belong to)

#### Create groups

`groupadd [-g GID] GROUP_NAME`

Ex:
- `groupadd web` => Adds the 'web' group.
- `groupadd -g 2500 db` => Adss the 'db' group and also explicitly sets the GID to 2500.

#### Delete a group

`groupdel GROUP_NAME`

Ex:
- `groupdel db` => Deletes the 'db' group.

#### Modify a group:

`groupmod [options] group_name`

Options are:
- `-g GID` => Change group ID to specified GID.
- `-n GROUP` => Change group name to specified name 'GROUP'.

## Special permission modes

When we start a process(execution), it runs using the User's UID and GID (we may have run it as others used 'su'/'sudo' etc for root, doesn't matter.)


### The setuid bit

**`setuid`**

We can explicitly set a UID before execution of a process:
- `setuid` => Set User ID upon execution.
- `setuid` FORCES the process to run as THE OWNER of the file regardless of who executes it.

How to check/tell if setuid is enabled?:
- `ls -l` => `-rwsrw-r-x ..`  The 's' in the Owner's execution field(x) tells that setuid is enabled.

Examples of commands and files that run with setuid/as owner of the file:
1. '/usr/bin/passwd' (Ex: need to be owner when changing the password)
2. `ping` command (Needs root privileges)
3. `chsh` command - Allows users to update their shell, etc...

#### Security measures

- It is prone to attack by hackers/malicious users since it always runs on owner(usually root) access.
- It is not honored on shell scripts - Scripts will execute as user who runs the script even if the setuid bit is set for the script. (Only 'binary executable' files work with setuid bit enabled)

#### Octal permissions

- setuid: 0, setgid: 0, sticky: 0 => Value for OFF (total 0)
- setuid: 1, setgid: 1, sticky: 1 => Binary Value for ON (total 3)
- setuid: 4, setgid: 2, sticky: 1 => Base 10 Value for ON (total 7)

Good: 4755 or below, Bad: 4775, Really bad: 4777 (anyone can edit the file!)

(Ex: 4775 or 4777 is what an attacker hopes to find in your system if they break in! - they can do anything they want to that file and maybe get root permissions.)

#### Adding the setuid attribute to a file

We can use the `chmod` command. Ex: 
1. `chmod u+s /path/to/file` (symbolic notation)
2. `chmod 4755 /path/to/file` (octal notation) - the ADD to MSBit 4, the setuid bit/special bit

#### Removing the setuid attribute from a file

Again, we can use the `chmod` command. Ex: 
1. `chmod u-s /path/to/file` (symbolic notation)
2. `chmod 0755 /path/to/file` (octal notation) - '0' => setuid disabled

#### Find all the files on the system that have setuid set

- `find / -perm /4000`,
(or, older style:)
- `fidn / -perm +4000`


### The setgid bit

**`setgid`**

`setgid` => Set Group ID upon execution. (Ex: `-rwxr-sr-x ..` => The execution bit(x) of the 'group' is set to 's' - setgid enabled)

#### Examples of commands using this setgid bit

- `/usr/bin/wall` : anybody who can edit this file can write whatever they want to the terminal(check).

#### Finding setgid files

- `find / -perm /2000`,
(or, older style:)
- `find / -perm +2000`

#### Adding setgid permission

We can use the `chmod` command. Ex: 
1. `chmod g+s /path/to/file` (symbolic notation)
2. `chmod 2755 /path/to/file` (octal notation) - the ADD to MSBit 2, the setgid bit/special bit

#### Removing the setgid attribute from a file

Again, we can use the `chmod` command. Ex: 
1. `chmod g-s /path/to/file` (symbolic notation)
2. `chmod 0755 /path/to/file` (octal notation) - SUBTRACT 2 from special permissons field

#### Adding both setuid and setgid

1. `chmod ug+s /path/to/file` (symbolic notation)
2. `chmod 6755 /path/to/file` (octal notation)

NOTE:
1. Setting the 'setgid' on a Directory causes: 'New' Files & Directories inside the directory to "inherit" the group of the directory. (Pre-existing files/directories within the directory are NOT affected by the setgid.)
2. Because of the above point, 'setgid' is "great for working with 'groups'". We can create a folder with a group's GID and appropriate/desired group permissions to the directory. So, whatever is added/deleted/modified inside the directory can be accessed by everyone belonging to the group (Shared folder).

** THIRD PARTY TOOLS TO CHECK FOR SETUID AND SETGID ON FILES (alternatives to 'find'): **

Ex: tripwire, AIDE, OSSEC, Samhain, Package managers

### The sticky bit

Used on a directory to ONLY allow the OWNER of the file/directory to RENAME (or) DELETE the file. Without the sticky bit set, another user to delete a user's files IF the permissions(777, say) allowed for it. Sticky Bit reperesented by 't' on others(o). (Ex: `-rwxr-xr-t ...`)

Example: Used on '/tmp' or '/var/tmp'

#### Adding the sticky bit

We can use the `chmod` command. Ex: 
1. `chmod o+s /path/to/file` (symbolic notation)
2. `chmod 1777 /path/to/file` (octal notation) - the ADD to MSBit 1, the special bit

(You would typically set sticky bit on 777 permissions because that is where it makes sense to use the sticky bit to only allow user to rename/delete the files/directories even when everyone else has permissions for it.)

#### Removing the sticky bit

We can use the `chmod` command. Ex: 
1. `chmod o-t /path/to/file` (symbolic notation)
2. `chmod 0777 /path/to/file` (octal notation) - the SUBTRACT 1 from the special bit


#### Reading the ls command output

Capitalized special permission bit => Means underlying normal permissions are NOT set.
- Ex: `-rwSr-xr-- ..`
- Ex: `-rwxr-xr-T ..`

Lowercase special permission bit => Means underlying normal permissions are SET.
- Ex: `-rwsr-xr-- ..`
- Ex: `-rwxr-xr-t ..`

## Networking


### TCP/IP:

The defacto standard for communication. 
- TCP - controls data exchange
- IP - sends data from one device to another
- Hosts - Devices on a network.

#### IPv4 Classes

```
1.0- 127.0 				= Class A 	(Subnet Mask: 255.0.0.0)
128.0 - 191.255 			= Class B 	(Subnet Mask: 255.255.0.0)
192.0.0 - 223.255.255 			= Class C 	(Subnet Mask: 255.255.255.0)
```

#### Classless Inter-Domain Routing

**CIDR**

Dividing networks irrespective of their classes. Division depends on subnet mask. Ex:

CIDR Subnet: 255.255.255.0 (given)
N/W Address: 121.67.198.0		(According to class A, it would have been 121.0.0.0)
B/C Address: 121.67.198.255		(According to class A, it would have been 121.255.255.255)

#### Reserved private address space

Ranges of IP addresses reserved for use in private (Non-Routable address spaces):
- 10.0.0.0 to 10.255.255.255 => Reserved private address space in class A.
- 172.16.0.0 to 172.31.255.255 => Reserved private address space in class B.
- 192.168.0.0 to 192.168.255.255 => Reserved private address space in class C.

Any of these IP address entries in the hosts file (/etc/hosts) is considered private and non-routable publicly.

#### Knowing the host computer IP address

**(Or, all IPs associated with your computer)**

Command: `ip address` (or) `ip address show`

(Shortcuts: `ip addr` (or) `ip a` (or) `ip a s`)

(Not available in Unix (Only Linux) - use `ifconfig` for unix.)

This command shows two addresses:
1. `lo: inet:127.0.0.1` => Your loopback address. (lo stands for 'loopback')
2. `eth0: inet:192.168.1.122/24` => Actually hardware NIC device - has an IP address associated.

(Also, it shows MAC addresses and Subnet Masks)

#### Another way to determine the host IP address

**`ifconfig`**

Another way to determine host's IP addresses. (DEPRECATED, but still very useful-maybe around for sometime)

Command: `ifconfig` => Displays all the IP addresses associated with the computer.

Terms:
- HOST : A device connected to a Network.
- HOSTNAME : A human readbale format for the IP address of a host (Ex: webprod1 <=> 10.109.215.14) (Ex: We can give a linux system acting as a server a hostname instead of addressing it by IP all the time.) One word Host name: Short Hostname / Unqualified Hostname (Ex: webprod1)
- DNS: Maps IP address to the domain name (and vice versa)

#### DNS Hostnames

- FQDN => Fully Qualified Domain Names. (Ex: webprod1.mycompany.com)
- TLD => Top Level Domain (Ex: .com, .org, .net, ...)

#### Domains

**(To the LEFT of the TLDs (Below the TLDs in the tree) (Ex: 'mycompany' in mycompany.com)**

Domains can be further sub-divided into: Sub-Domain => To the LEFT of the Domains (Below the Domains in the tree) (Ex: 'webprod1' in webprod1.mycompany.com)

An advantage of using sub-domains: Identifying where our server is located: (Ex: webprod1.ny.us.mycompany.com) [NOTE: Sub-Domains need not correspond to geography, can be anything]

#### Viewing the hostname

- `hostname` 
(or)
- `uname -n`
(or)
- `hostname -f`

#### Setting the hostname

- `hostname HOST_NAME` => sets the host name to specified argument(ex: `hostname webprod02`)

To persist the change, (permanently set the hostname btw sessions):
1. UBUNTU AND REDHAT SYSTEMS:
`echo 'webprod02' > /etc/hostname` (or, edit the file and put the hostname as a line)
(or)
2. FOR EARLIER VERSIONS OF REDHAT:
Save the line 'HOSTNAME=webprod02' in '/etc/sysconfig/network' file

#### Resolving DNS names

Get IP from Hostname and Hostname from IP:
- `host HOSTNAME` => Displays the IP for the hostname (Ex: for the hostname 'www.mycompany.com')
- `host IPADDRESS` => Displays the Hostname for the IP (Ex: for the IP '11.2.255.143')

#### The hosts file

**`/etc/hosts`**

Contains a list of IP addresses and Hostnames. We can add hosts as an entry to the file:

Format: `ipaddress FQDN alias(es)` => Maps IP address to hostname (or hostnames)

Ex:
- `10.11.12.13 webprod02.mycorp.com webprod02`

Now, we can access the IP address using the specified Hostnames.

Points:
- (THIS CAN BE USEFUL IF YOU WANT TO ACCESS COMPUTERS THAT DON'T HAVE DNS HOSTNAMES(for ex))
- (HOSTNAMES IN THE '/etc/hosts' IS USED TO OVERRIDE THE DNS HOSTNAMES FOR THE SYSTEM - Ex. you can have a private network for a cluster of web servers that you own that only they and no one else can access - Create private IP addresses for each of the servers in the '/etc/hosts' file thus forcing each of the servers to go through the private network to communicate with each other.)

Note: '/etc/hosts' file is LOCAL to your Linux System. It does NOT propagate to the Rest of the Network.
- `127.0.0.1 localhost` entry => Used by system as loopback address.

NOTE:: The '/etc/hosts' file is checked first before the DNS is queried.(for search resolutions). We can change this lookup/search resolution order in the '/etc/nsswitch.conf' file.(controls the search order for resolutions)
- `hosts: files dns`	=> (If IP address is found in /etc/hosts, it is used. Search stops. Else, check DNS)
- `hosts: files nis dns` => (First check in files, then NIS, then DNS)

## DHCP static and dynamic addressing

### Ports

Ports identify a service on a host (while IP identifies a host).
- 0 - 1023 are 'Well-Known'(system) Ports.
- Ex:Port No. 22 = SSH,
- 25 = SMTP,
- 80 = HTTP,
- 143 = IMAP,
- 389 = LDAP,
- 443 = HTTPS (Ex: https://www.mybank.com)

It requires Superuser/Root privileges to open the Well Known Ports(0-1023). (Hence 'Privileged Ports')

Ports above 1023(1024+) can be opened and used by normal users on the system(need not be root/superuser) (1024+ => Unprivileged Ports)

Port Names: '/etc/services'. Maps port names to port numbers (Human readable port names)
Ex:
- `ssh 	22/tcp 		# SSH Remote Login Protocol`
- `smtp 	25/tcp 		# SMTP`

Sometimes, when a third party service is installed, we can ADD a port number and name for the service it provides in the '/etc/services' file. (Therefore, we can also set port numbers for the custom applications/services that we write)

### DHCP

PRIMARY USE: TO ASSIGN IP ADDRESSES TO HOSTS ON A NETWORK.

Dynamic Host Control Protocol. When a DHCP (host) client wants an IP address to itself, it sends out a B/C msg looking for DHCP Servers to assign it an IP address. 'DHCP Servers' assign IP address to DHCP Clients.

Format of Information provided by DHCP Server to Client:
1. IP address
2. netmask
3. gateway
4. DNS servers

The DHCP client then configures itself with this information and communicates with others using the given IP.

Each IP is 'leased' from the pool of IP addresses that the DHCP server manages.(The lease expiration time is configurable on the DHCP server. 1hr, 1day, 1Weeks. The client must renew the Ip address if it wantsto continue using it. Otherwise, the IP address is available to other DHCP clients for use.)

#### Configuring a DHCP Client

**For a RedHat Based System(RHEL)**

To Edit a Red Hat based system as a DHCP Client, edit the configuration file located in: `/etc/sysconfig/network-scripts/ifcfg-DEVICE`. Ex: 
- `/etc/sysconfig/network-scripts/ifcfg-eth0`,
- `/etc/sysconfig/network-scripts/ifcfg-enp5s2`

To get a list of Network Devices on the system, run:
- `ifconfig -a`
(or)
- `ip link`

Once you have identified the configuration file for the network device: Set the 'BOOTPROTO' variable to 'dhcp':
- `BOOTPROTO=dhcp`

#### Configuring an Ubuntu based System

Edit the '/etc/network/interfaces' file. Set a network device as a DHCP Client: Add line `iface NETWORK_DEVICE inet dhcp`
Ex:
- `iface eth0 inet dhcp`

1. Setting a STATIC IP address on REDHAT Based system(RHEL):

Edit file: '/etc/sysconfig/network-scripts/ifcfg-NETWORKDEVICENAME'. Ex:
```
	DEVICE=eth0
	BOOTPROTO=static 	(This is a MUST!!)
	IPADDR=10.109.155.174	(Assign the IP, NW and BC)
	NETMASK=255.255.255.0
	NETWORK=10.109.155.0
	BROADCAST=10.109.155.255
	GATEWAY=10.109.155.1
	ONBOOT=yes				(To set the Ip address on boot? yes)
```

2. Setting a STATIC IP address on UBUNTU Based system(RHEL):

Edit file: '/etc/network/interfaces' Ex:
```
iface eth0 inet static 		(static keyword is a must!!)
address 10.109.155.174
netmask 255.255.255.0
gateway 10.109.155.1
```

(OR)

- MANUALLY assign an IP to a Network Device(interface): Use the `ip` command.
	
Format: `ip address add IP/[NETMASK] dev NETWORK_DEVICE`. Ex:
- `ip address add 10.11.12.13 dev eth0`,
- `ip address add 10.11.12.13/255.255.255.0 dev eth0`.

NOTE:
Bring the interface up(enabled with the given static ip): `ip link set NETWORK_DEVICE up` => Enables/sets up N/w Device with given IP (Ex: `ip link set eth0 up`)

- Use the `ifconfig` command.

Format: `ifconfig NETWORK_DEVICE IP_ADDRESS netmask SUBNET_MASK`

Ex:
- `ifconfig eth0 10.11.12.13`
- `ifconfig eth0 10.11.12.13 netmask 255.255.255.0`

NOTE: Bring the interface up(enabled with the given static ip): `ifonfig NETWORK_DEVICE up` => Enables/sets up N/w Device with given IP (Ex: `ifonfig eth0 up`)

Alternatives to `ip` and `ifconfig`:
- `ifup` and `ifdown` => Quick way to bring a NW device up or down. It takes the network specs(IP, mask, etc) for the NW Device from the "configuration files" and enables/disables it. (/etc/sysconfig/... etc)

Ex:
- `ifup NW_DEVICE` => brings up the network device (Ex: `ifup eth0`)
- `ifdown NW_DEVICE` => brings down the network device (Ex: `ifup enp5s02`)

### GUI or TUI Tools for networking

- RedHat => 'nmtui', 'system-config-network'
- SUSE => 'YaST'
- Ubuntu => No official tool available.

## Network troubleshooting

Some of the common tools for network diagnostics. Cannot rely on only one tool/ use many tool.

### Test connectivity to a host with ping

**`ping`**

Sends one or more ICMP packets to a host (Hostname (or) IP-ADDRESS) and waits for a reply
- `ping HOST` => Continuously pings the host until you stop program with `<CTRL-C>` (ex: `ping google.com`)
- `ping -c COUNT HOST` => Specifies the number of packets to send with ping (stops after sending these) (Ex: `ping -c 3 google.com`, `ping -c 3 10.1.244.101`, .. etc.)

Ping returns the no of packets sent and Round Trip time(RTT) for each packet( '/' separated ) - In case of no replies from host: `100% packet loss` is displayed in output.

Note: Ping also resolves the Hostname to IP address (If it cant => Unknown host error displayed - In that use IP address of system that you are trying to connect to.)

NOTE: If ping does NOT receive a repsonse from destination host:
1. Check if ping works to a local host in the network. If that also does NOT work then maybe there is a problem with OUR SYSTEM(OUR HOST) itself. Ex: Network cables got disconnected, NW drivers didn't get upgraded when Server System was upgraded, ... etc.
2. If we can successfully ping a host within our local network: Then the problem lies outside of our network and definitely not on our host(our computer). If we can successfully ping other external hosts, the problem might be with one particular host that w pinged initially. (Ex: google.com ping fails but youtube.com and facebook.com pings are successful). POSSIBLE REASON: The destination host has a 'firewall' that has blocked/discarded icmp requests and responses. In this case, it will require other diagnostic tools other than 'ping'.


### Testing connectivity over Hops

**Hops => Routers**

Use the `traceroute` command. (`ping` only gives you the end to end connectivity info)
- `traceroute` will require ROOT/SUPERUSER permissions.

- `traceroute IP_ADDRESS` => Goes to DNS and resolves to name(TIME taking)

- `traceroute -n HOST_NAME` => Skips the DNS server and directly to IP of host (Ex:`traceroute -n google.com`)

Advantages: 
- skips DNS - If issue was with DNS server then we will know. 
- Faster. 

#### Output of traceroute

Lists all the router IPs along the way(route) along witht the milliseconds it took for the packets to cross that network. Too much time? => Maybe problem is in that network. '*' for time => Either n/w not responding (or, router configured to not show traceroute - use other diagnostic tool)

`traceroute` Produces one line of output per HOP.

#### Alternative to traceroute

**`tracepath`**
 
Use `tracepath`. Does NOT require root/superuser permissions

Ex:
- `tracepath google.com` (or)
- `tracepath -n google.com` => Produces one line of output for Each Response it receives.(unlike traceroute)

### The netstat command

**`netstat`**

Used to collect a wide variety of network information.

Options:
- `-n` => Display numerical addresses and ports
- `-i` => Display list of network interfaces
- `-r` => Display the route table (Ex: `netstat -rn`)
- `-p` => Display PID and Program used [Needs root/superuser privileges]
- `-l` => Display listening sockets(ex:`netstat -nlp`){What servers(nginx,apache) are listeningto what ports}
- `-t` => Limit output to TCP (ex: `netstat -nltp`)
- `-u` => Limit output to UDP (ex: `netstat -nulp`)

Ex:
- `netstat -i`
- `sudo netstat -nltp`

### Packet sniffing with tcpdump

**`tcpdump`**

`tcpdump` => Inspect contents of network packets to ensure payloads(data) are actually being delivered. (Requires root/superuser privileges)

Options:
- `-n` => Display numerical addresses and ports (suppresses DNS queries as well)
- `-A` => Display ASCII(text) output.
- `-v` => Verbose mode. Produces more output
- `-vvv` => Even more verbose output.

(`tcpdump` output: timestamp, nw id, source id, portnos, pkt spec info. etc)

Ex:
- `sudo tcpdump` => Produces output for all the packets from/to the network devices assoc. with the system.

### The obsolete telnet command

**`telnet`**

It was originally intended to log onto 'remote systems' but is replaced with with better protocols such as SSH.

'telnet' can still be used in N/W TROUBLE SHOOTING. (May or may not be installed by default on linux systems - bcoz it is obsolete for connectin to systems)

Usage of telnet: Initiate a TCP Connection to a host (or ip) by specifying the port.

Format: `telnet HOST_OR_IP PORT_NO`

Ex: Check if google.com is accepting requests at the HTTP port?:
- `telnet google.com 80` => If successfully connected - "Connected to google.com" or similar o/p. (If operation "timed out" - means connection could not be established - either port is not open on the host(firewall) [or] the connection to the host could not be made along the way/route)

About `telnet`:
- Telnet command prompt: `telnet> `
- To put a 'GET' request to, say, root directory: `GET /`

Quit telnet: Press `quit` at the telnet prompt. (Output is: "closed")


## Connecting via SSH to a Linux Virtual Machine

**(Running on VirtualBox)**

1. Power Off virtual machine from VBOX.
2. Goto Settings for that machine in VBOX.
3. Change network setting to 'bridge adapter' (from NAT) and save.
4. Power on Virtual Machine -> Open Terminal -> `ip addr` -> Get the ip address of the Network Interface Device (Other than local/loopback address) (= VM_IP_ADDRESS)
5. `whoami` => to know the username on the VMachine (= VM_USERNAME) (Sometimes, we cannot connect using the root username so switch to another user and get his/her username)
6. Open terminal on your Local Machine while your VMachine is running on VBOX.
7. Type `ssh VM_USERNAME@VM_IP_ADDRESS` (Ex: `ssh adminuser@192.168.0.1`)
8. You will prompted to accept the key(say 'yes') and type the password for that user on the virtual m/c/
9. You are logged into the VMachine via SSH! :)

**THE END**



















