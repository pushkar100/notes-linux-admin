# Basic CLI Commands:

Commands are case-sensitive! : All commands are `lowercase`.

- [Basic CLI Commands:](#basic-cli-commands-)
  * [Very Simple Commands:](#very-simple-commands-)
  * [Linux Directory Structure:](#linux-directory-structure-)
  * [Linux Links:](#linux-links-)
    + [Inode:](#inode-)
    + [Soft Links (or) Symbolic Link:  (For both files and directories)](#soft-links--or--symbolic-link----for-both-files-and-directories-)
    + [Hard Links:  (Only for Files)](#hard-links----only-for-files-)
    + [Creating Hard Links: `ln orginalFilePath newFilePath`](#creating-hard-links---ln-orginalfilepath-newfilepath-)
    + [Creating Soft Links: `ln -s originalFilePath newFilePath`](#creating-soft-links---ln--s-originalfilepath-newfilepath-)
  * [`ls` Command Options (-):](#-ls--command-options-----)
  * [`touch` Command:](#-touch--command-)
  * [Make and Remove Empty Directories:](#make-and-remove-empty-directories-)
  * [Remove Files and Non-Empty/Empty Directories:](#remove-files-and-non-empty-empty-directories-)
    + [With `-i` Option:](#with---i--option-)
    + [With `-f` Option:](#with---f--option-)
    + [With `-v` option(verbose):](#with---v--option-verbose--)
    + [For Deleting Directories:](#for-deleting-directories-)
    + [Deleting Files and Directories together:](#deleting-files-and-directories-together-)
  * [Copying Files: (Duplicating Files)](#copying-files---duplicating-files-)
    + [Copying files into a directory:](#copying-files-into-a-directory-)
    + [Copying Directories/Files into a directory:](#copying-directories-files-into-a-directory-)
      - [`-i` (Interactive) Flag:](#--i---interactive--flag-)
      - [`-v` (Verbose) Flag:](#--v---verbose--flag-)
  * [Renaming & Moving(Cut-Paste) Files:](#renaming---moving-cut-paste--files-)
    + [Renaming Files:](#renaming-files-)
    + [Renaming a Directory:](#renaming-a-directory-)
    + [Moving (Cut-Paste) Files:](#moving--cut-paste--files-)
    + [Moving (Cut-Paste) Directories:](#moving--cut-paste--directories-)
    + [`-i` (Interactive) Flag:](#--i---interactive--flag--1)
  * [File Extensions in Linux:](#file-extensions-in-linux-)
    + [How to know the TRUE TYPE of a File/Directory?](#how-to-know-the-true-type-of-a-file-directory-)
    + [File and Directory Names with Spaces:](#file-and-directory-names-with-spaces-)
  * [File and Directory Names with Special Characters:](#file-and-directory-names-with-special-characters-)
    + [The TWO characters we can NEVER use in a File or Directory Name:](#the-two-characters-we-can-never-use-in-a-file-or-directory-name-)
  * [AUTOCOMPLETION:](#autocompletion-)
  * [Keyboard Shortcuts:](#keyboard-shortcuts-)
  * [Graphical Text Editor:](#graphical-text-editor-)
  * [Terminal Text Editors:](#terminal-text-editors-)
    + [`nano` editor:](#-nano--editor-)
  * [History of Commands:](#history-of-commands-)
  * [Viewing Text Files (Read-only mode):](#viewing-text-files--read-only-mode--)
    + [`less` command:](#-less--command-)
    + [`cat` command:](#-cat--command-)
    + [`tac` command:](#-tac--command-)
    + [`head` and `tail` commands:](#-head--and--tail--commands-)
  * [Counting Words in a Files:](#counting-words-in-a-files-)
  * [Types of Linux Commands:](#types-of-linux-commands-)
    + [Finding the Type of a Command:](#finding-the-type-of-a-command-)
    + [Finding the Location of an Executable Command:](#finding-the-location-of-an-executable-command-)
  * [Description/Information about Commands:](#description-information-about-commands-)
  * [Executing Multiple Commands:](#executing-multiple-commands-)
  * [Wildcards:](#wildcards-)
  * [Aliases:](#aliases-)
    + [Deleting an Alias:](#deleting-an-alias-)
    + [The `~/.bashrc` file:](#the----bashrc--file-)


## Very Simple Commands:

- `date` = Returns the current time of the system(day, month, date, time, year)
- `cal` = Displays the calendar for current month(default) [can also use `cal -1`]
	- `cal -y` = Displays calendar for whole current year.
	- `cal YYYY` = Displays calendar the whole year YYYY.
	- `cal X YYYY` (or)`cal XX YYYY` = Displays calendar for month X of year YYYY.
	- `cal -3` = Displays calendar for Previous month, Current month, and Next month of current year.

- `clear` = clears the terminal screen - clears previous commands and outputs (blank slate)
- `exit` = exits the current terminal session

## Linux Directory Structure:

Folders in windows are known as 'Directories' in Linux although both mean the same thing. (Used Interchangeably)

The Directory structure is Tree-like where `root` (Represented by `/`) forms the top-most node.

First Level : `root` or `/`
Next Level : 	
- `bin`		= Executable binaries stored here
- `opt`		= Stores files NOT installed by default by the OS. Ex: Google Chrome files
- `home`	= Every User has a unique directory under the `home` directory under which he can store his own folders and files
- `tmp`		= Stores temporary files - do not store imp files here
- `var`		= Variables, log files, databases, etc
.... and so on.

When you login to system as a user, you're Current Working Directory is automatically set to your(user's) home folder.

- Absolute Paths: Start from `root`. Ex: `/home/pushkar` (Absolute paths start with `/`)
- Relative Paths: Start from Current Working Directory(.) Ex: `./Desktop` or simply `Desktop` if user is in directory containing the Desktop folder

- `pwd` = Print Working Directory (Displays the absolute pathname of the current working directory).
- `cd` = Changes Current Working Directory to path specified (Ex: cd Desktop) (Can use Absolute/Relative Paths)
	- `cd /` = Takes user to Root(/) directory
	- `cd ~` (or) `cd` = Takes user to his/her Home(~) directory
	- `cd ..` = Takes user to the Parent directory (of the current working directory)
	- `cd .` = Takes user to the current working directory (NO CHANGE) [USELESS TO RUN THIS COMMAND]
	- `cd -` = Takes user to his/her Previous Working Directory (Ex: user changed directory from home to root, running `cd -` will take him back to home)

- `ls` = Lists the Current Directory's contents [Default] (ie. Lists files and folders inside current folder)
	- `ls /` = Lists contents of Root(/) directory.
	- `ls ~` = Lists contents of User's Home(~) directory.
	- `ls ..` = Lists contents of Parent Directory (of Current Working Directory)
	- `ls .` = Lists contents of Current Working Directory (REDUNDANT -> SAME AS `ls`)
	- `ls /absolute/path/name` = Lists contents of Directory listed by the absolute path
	- `ls relative/path/name` = List contents of Directory listed by the relative path

NOTE: `ls -` does NOT list contents of Previous Working Directory (`-` is seen as a flag/option in `ls`)

Getting the basename of the file/directory:
- `basename fileOrDirPath` = returns just the filename/Directory name after stripping off the path to the file.

Getting the directory of the file/directory:
- `dirname fileOrDirPath` = Returns directory path to the file, stripping off the file name. (Opp. of basename)

## Linux Links:

### Inode:

- Every file in the system has an inode(Index Node)
- It contains all the information except 'file contents' and 'file name'
- Just like a personal ID or a Passport but Without a name!

Inodes contain the following:
- Inode number 
- File Size
- Owner Information
- Permissions
- File Type
- Number of Links (Etc ...)

### Soft Links (or) Symbolic Link:  (For both files and directories)

(These are similar to 'Shortcuts' for files on Windows)

- It's a pointer to the original file
- Just like shortcut in windows
- It has a DIFFERENT Inode Number (Different from the Inode number of the original file)
- Has a SMALLER file size (Significantly smaller file size)

**Important!:**
- Soft links will contain the SAME data as the Original file
- CHANGING contents of one file will change the contents of the other soft linked files and original file as well.
- IF we "DELETE" the original file, the soft links will become "USELESS" (Since they were pointers to the original file)

Therefore, we cannot even open/use the softlinks after the original file has been deleted. (Similar to shortcuts in Windows which will not work if we delete the original file)

### Hard Links:  (Only for Files)

- Has a different name of the same(original) file 
- Has SAME file size
- SAME Inode Number

Actually, there is nothing like original file since both point to the same file and can't be differentiated. (You can think of a hard link as a copy of the original file but not as a shortcut)

**Important!:**
- Hard Links will contain the SAME data as the Original File
- CHANGING contents of one file will change the contents of the other hard linked files(incl. original) as well.
- DELETING the original file will NOT affect the contents of the Hard Link files.

- `ls -i` = Lists contents of directory(CWD b Default) displaying the 'inode number' next to the files/directories listed. (Ex: `ls -i /` lists inode numbers of files/directories contained withing the Root(/) directory)
- `ls -l` = Lists contents of a directory in a 'Long Listing Format'. 

Format: 
1. Is it Directory? 
2. File permissions 
3. Owner of File 
4. Group assigned to File
5. Number of links
6. File size in bytes
7. Date and Time of Last Modification
8. File name


### Creating Hard Links: `ln orginalFilePath newFilePath`

Ex: `ln sample.txt newSample.txt`
- Running `ls -i` now will give the same(exact) inode number for both the sample.txt and newSample.txt files
- Running `ls -l` now will give the same(exact) file size(bytes) for both the sample.txt and newSample.txt files

### Creating Soft Links: `ln -s originalFilePath newFilePath`

Pass `-s` option to indicate a soft link. Ex: `ln -s sample.txt newSample.txt`

Soft links show '-> original file' pointer when we do an `ls -l`

NOTE: Hard links cannot be created for directories - Throws an error!. But we can create softlinks for directories like: `ln -s originalDirPath newDirPath`

We can create an Infinite Directory Loop using Soft Links. Ex: Existing folders - '/a' and '/a/b':
- `cd /a/b`
- `ln -s .. c`
Since we used a softlink(c) to b's parent(a) inside b, clicking b and c will repeatedly open new directories in a loop
That is: a/b/c/b/c/b/c/b/c... etc.

## `ls` Command Options (-): 

General Syntax: `ls [options] [/path/to/dir]`

- `ls` = Lists files in Alphabetical Order by default. (Lists from CWD if Directory path is not given.)
- `ls -a` = This will list all the files in your current working directories including hidden files that start with '.'
- `ls -l` = Lists contents of a directory in a 'Long Listing Format'. 
		(Format: 
			Is it Directory?, File permissions, Owner of File, Group assigned to File, Number of links, File size in bytes, Date and Time of Last Modification, File name
		)
- `ls -t` = This will list the files sorted by modification date. Newest first.
- `ls -r` = This will list the files in reversed fashion. (Reverse Alphabetical Fashion by default).
		
Ex: `ls -tr` lists all the files in the specified directory in reverse time order. Oldest First.

- `ls -R` = This will RECURSIVELY list all the files and directories from the specified directory (CWD if not specified).

Ex: `ls -Ra /` will list all the files on your system including hidden files and folders.(HEAVY COMPUTATION)

- `ls -i` = This will list the index node number of each file in the current working directory.

Note: We can combine multiple options: Ex: `ls -Rat` = Lists all files/Directories Recursively including hidden files in modification time order(newest first).

## `touch` Command: 

To Create a new empty file PLUS to modify time of existing files.

- `touch existingFilePath` = Used to update last modification time of file to current time.
- `touch existingFilePath1 existingFilePath2 ..` = Used to update last modification time of listed files to current time.
- `touch newFilePath` = Used to Create a new empty file (@specified location)

## Make and Remove Empty Directories:

- `mkdir directoryPath` = Makes a new Empty Directory at specified path.
- `mkdir directoryPath1 directoryPath2 ...` = Makes new Empty Directories at specified paths.

- `rmdir directoryPath` = Deletes the specified Empty Directory from the system.
- `rmdir directoryPath1 directoryPath2 ...` =  Deletes all the specified Empty Directories from system.

NOTE: `rmdir` command **fails** to **remove non-empty directories** (throws an error message).

## Remove Files and Non-Empty/Empty Directories:

- `rm filePath` = Deletes the specified file from the system.
- `rm filePath1 filePath2 ..` = Deletes files specified from the system.

### With `-i` Option:

Interactive : Ask for confirmation.

- `rm -i filePath` = Asks for confirmation from user before the removal of specified file.
- `rm -i filePath1 filePath2 ..` = Asks for confirmation from user before the removal of all the specified files.

### With `-f` Option:

Force : Opposite of `-i`, No confirmation/prompt.

- `rm -f filePath` = forcefully deletes specified file.
- `rm -f filePath1 filePath2 ..` = forcefully deletes all the specified files.

Ex: Even if you try deleting a non-existent file, which usually throws an error, with `-f` the command gets executed and does not throw an error : Therefore: `-f` ignores non-existent files.

### With `-v` option(verbose):

- `rm -v filePath` = Deletes specified file and prints a summary.
- `rm -v filePath1 filePath2 ..` = Deletes all the specified files and prints a summary.

### For Deleting Directories: 

**`-R` Flag is a must!** 

`-R` for this command is NOT case-sensitive!! (`-r` works too!)

- `rm -R directoryPath` = Deletes the specified directory(empty/not) from the system(along with all its contents)
- `rm -R directoryPath1 directoryPath2 directoryPath3` = Deletes all the specified directories(and their contents)

- `rm -iR dirPath` = Asks for confirmation from user before the removal of specified dir and for each of its files and sub-directories.
- `rm -iR dirPath1 dirPath2 ..` = Asks for confirmation from user before the removal of all the specified Directories and each of their files and sub-directories.

The `-R` flag is necessary while deleting Directories. It means delete the directory by deleting everything inside it "recursively".

- `rm -Rf dirPath` = removes directory and it's files/subdirs without confirmation and ignores non-existent dirs/files.
- `rm -Rf dirPath1 dirPath2 ..` = removes directory and it's files/subdirs without confirmation and ignores non-existent 	dirs/files.

- `rm -Rv dirPath` = Deletes specified directory and prints a summary.
- `rm -Rv dirPath1 dirPath2 ..` = Deletes all the specified directories and prints a summary.

### Deleting Files and Directories together:

- `rm -R dirPath1 filePath2 ..` = Since we are deleting directories as well, we need -R flag.

**Dangerous Command:**

- `rm -rf /` = Deletes all files on your system without confirmation! (DON'T RUN IT) (Nowadays, some OSes protect against the execution of this command)

## Copying Files: (Duplicating Files)

- `cp sourceFilePath destinationFilePath` = copies contents of source file to destination file

NOTE:
- If destination does NOT exist = the destination file is CREATED having the contents of the source file.
- If destination does EXISTS = the destination file is MODIFIED to have the contents of the source file.

### Copying files into a directory:

- `cp sourceFilePath1 sourceFilePath2 ... destinationDirectoryPath` = Copies all the specified files into the destination folder.

### Copying Directories/Files into a directory:  

Require `-R` option : Recursive.

- `cp -R sourceDirectoryPath destinationDirectoryPath` = Copies the specified directory into the destination folder.

NOTE: When copying file/directory into a destination directory, any existing file in the destination that has the same name is overridden/overwritten.

#### `-i` (Interactive) Flag:

Used to Confirm/Prompt if same name files/dirs in the destination directory need to be overridden/not!

- `cp -i sourceFilePath destinationDirectoryPath`

#### `-v` (Verbose) Flag:

Same as normal `cp` command but it prints a summary after execution.

- `cp -v sourceFilePath destinationFilePath`

## Renaming & Moving(Cut-Paste) Files:

### Renaming Files:

- `mv oldFileName newFileName` = Renames file with the new name. The newFileName should NOT exist.

### Renaming a Directory: 

Same way as renaming a file

- `mv oldDirName newDirName` = Renames Directory with the new name. The newDirName should NOT exist.

We can even rename a file/directory into a hidden name by prepending '.' to the new name & vice-versa!

### Moving (Cut-Paste) Files:

- `mv sourceFilePath destinationDirectoryPath` = Move(Cut) source file into destination Directory.
- `mv sourceFilePath1 sourceFilePath2 ... destinationDirectoryPath` = Move(Cut) source file into destination Directory.

Note: 
1. Destination folder MUST EXIST! 
2. Files with same name existing in destination directory will be Overridden/Overwritten by default

### Moving (Cut-Paste) Directories:

- `mv sourceDirectoryPath destinationDirectoryPath` = Move(Cut) source Directory into destination Directory.
- `mv sourceDirectoryPath1 sourceDirectoryPath2 ... destinationDirectoryPath` = Move(Cut) source directory into destination Folder.

Note:
- Destination folder MUST EXIST!.
- Directories with same name existing in destination directory will be Overridden/Overwritten by default.

Note: `mv` Command does NOT require `-R` flag that was required by the copy (`cp`) command!.

### `-i` (Interactive) Flag:

Used to Confirm/Prompt if same name files/dirs in the destination directory need to be overridden/not!
- `mv -i sourceFilePath destinationDirectoryPath`

## File Extensions in Linux:  

**File extensions in Linux have no meaning**

Linux file extensions don't have meaning. If you rename a file and change the extension or remove it, it will still open normally. Ex: 
- `rm tux.png penguin` = 'penguin' file will still open/can be opened as an image itself
- `rm a.zip cmpFile` = 'cmpFile' will still open/can be opened as a zip folder itself

### How to know the TRUE TYPE of a File/Directory?

- `file fileName` = Gives information about the type of the file. Ex:
	- `file penguin` = penguin: PNG image data, 1979 x 1979, 8-bit/color RGBA, non-interlaced
	- `file f` = f: ASCII text
	- `file dir1` = dir11: directory

- `file fileName1 fileName2 ..` = Gives Information about type of all the specified files/directories

### File and Directory Names with Spaces:  

Method 1: wrap them in quotes - Either single or double quotes
Ex: 
- `mkdir 'my dir'`, 
- `rmdir 'my dir'`,
- `touch 'my file'`, etc..

Method 2: Prepend one backslash(\) for every space in the file name
Ex: 
- `mkdir my\ dir`, 
- `rmdir my\ dir`,
- `touch my\ file`, 
- `touch my\ \ dog`, (two spaces), etc..

## File and Directory Names with Special Characters:  

The Special Characters are: 
```
$ 
> 
< 
& 
| 
; 
" 
' 
\
```
These need to be 'escaped' while using them as part of File names. We use backslash(\) to escape these special characters in file names:
Ex:
- `\$file1` = $file1
- `cats\&dogs` = cats&dogs
- `\$\$four\>three` = $$four>three
- `the\ \"quote\"` = the "quote"
- `why\\escape` = why\escape (escaping the backslash character itself)
- `escape\\\\twice` = escape\\twice (to include every 'n' blackslashes, we need '2n' backslashes in the name)

### The TWO characters we can NEVER use in a File or Directory Name:

1. '/' (forward slash) : Stands for root or as a separator in paths. Therefore, we cannot use it as file/directory name.
2. The NULL character : (Not so important right now)

## AUTOCOMPLETION:

Use the 'TAB' key to auto-complete: (Write a few characters and Hit Tab). We can autocomplete:
- File Names
- Directory Names
- Paths
- Commands
etc... the files/dirs/cmds must exist for auto-completion.

If multiple options exist, pressing TAB once more will list all the options below = SUGGESTIONS

If out of the multiple options, one of them is a substring of the other file, the shorter file name is autocompleted upon TAB. After this, if we type just one character of the bigger filename and hit TAB then it will auto-complete to that.

## Keyboard Shortcuts:

1. While typing a command on the terminal, if we want to move to the START character of the command then press `CTRL-A`
2. While typing a command on the terminal, if we want to DELETE the character which CURSOR POINTS to then press `CTRL-D`
3. While typing a command on the terminal, if we want to move to the END character of the command then press `CTRL-E`
4. While typing a command on the terminal, if we want to CUT text from CURRENT POSITION to the END of the command then press `CTRL-K` (To PASTE it BACK again, press `CTRL-Y`)
5. While typing a command on the terminal, if we want to CLEAR THE SCREEN then press `CTRL-L`.
6. While typing a command on the terminal, if we want to move to ONE WORD FORWARD then press `ALT-F` (DOES NOT WORK ON MAC KEYBOARD)
7. While typing a command on the terminal, if we want to move to ONE WORD BACKWARDS then press `ALT-B` (DOES NOT WORK ON MAC KEYBOARD)
8. While typing a command on the terminal, if we want to convert CURRENT WORD to UPPERCASE then press `ALT-U` (DOES NOT WORK ON MAC KEYBOARD)
9. While typing a command on the terminal, if we want to convert CURRENT WORD to UPPERCASE then press `ALT-L` (DOES NOT WORK ON MAC KEYBOARD)

## Graphical Text Editor:

The default Graphical Text Editor on linux is `gedit`.
- `gedit filePath` = Opens the text file mentioned in gedit.(a GUI program)

1. If file exists => gedit opens it for you
2. If file does NOT exist => gedit creates on and opens it for you

`gedit` DOES NOT WORK ON MAC by DEFAULT (Needs to be Installed)

## Terminal Text Editors:

There are many: Vi, Vim, Emacs, Nano .. etc

### `nano` editor:

`nano filePath` = Opens the text file mentioned in the terminal. Commands to be used on the editor are displayed inside the editor itself. Ex: ^X => CTRL+X => Exits Editor

- If file exists => nano opens it for you
- If file does NOT exist => nano creates on and opens it for you

## History of Commands:

Typing <Up-Arrow> will give us the previously type commands (Newest first). Linux could store ~500 commands by default.

- `history` = This command will list out all the recently used commands by you in a table format: serial number followed by the command.

- `history xx` = Shows you the last xx number of commands.

- `!xxx` = Reuse a command that you see in the history table, use: (Exclamation mark(!) followed by the command's serial number). Then the corresponding command gets executed.

The entire history is stored in a file called `.bash_history` (hidden file) in your Home(`~`) Folder. It contains all the previous commands, one command per line. We can edit this file in order to modify/delete/add to the command history(so that other users don't see it).

- `history -c` = Clears up your entire history. That is, `.bash_history` is emptied of its contents.

## Viewing Text Files (Read-only mode):

### `less` command:
- `less filePath` = less is a command that brings up the less text file viewer for the specified file. (less command takes you to a separate/dedicated screen)

'less' is a read only mode file viewer. We cannot edit files like we did in nano/gedit.
	
Inside less viewer: 
- Press `q` to exit less, 
- Press `h` to get help on less commands, 
- `/searchkey` to search for text, etc..

###  `cat` command:
- `cat filePath` = cat command is used to display(print) the contents of a text file on the terminal. (cat does not take you to a separate screen like with less command but shows contents on the terminal itself)

`cat` stands for 'catenating'

- `cat filePath1 filePath2 ...` = To view(print on terminal) two or more files by concatenating their contents. (Order of the files matter)

### `tac` command:

- `tac filePath` = Used exactly like `cat` but it reverses the file contents while printing (last line is first)
- `tac filePath1 filePath2 ...` = Used exactly like `cat` but it reverses each of the file contents (last line is first) and then concatenates them and prints content.

### `head` and `tail` commands:

- `head filePath` = Prints/Display the FIRST 10 lines of a file
- `head -n xx filePath` = Prints/Display the FIRST xx lines of a file

- `tail filePath` = Prints/Display the LAST 10 lines of a file
- `tail -n xx filePath` = Prints/Display the LAST xx lines of a file

## Counting Words in a Files:

- `wc filePath` = Prints the 1. number of lines, 2. number of words, and 3. number of bytes or characters in the specified file. (Any no.of chars (>=1) appearing together and separated from other such blocks by spaces is considered as a 'word')

- `wc -l filePath` = Prints only the number of lines.
- `wc -w filePath` = Prints only the number of words.
- `wc -c filePath` = Prints only the number of characters or bytes.
- `wc -L filePath` = Prints the Length(number of characters/bytes) of the Longest Line in the file. (capital 'L' flag)

## Types of Linux Commands:

All linux commands can be classified into one of the following types:

1. Executable Programs:
	- These are normal applications that get executed (Liks any other application on the system).
	- They are generally found in the '/bin' or '/usr/bin' folders.
	- Common Executable program application exampe => `cp` command

2. Shell built-ins:
	- These commands are built into the shell. Ex. The bash shell(Bourne Again) Shell .
	- A famous shell built-in command is the : `cd` command.

3. Shell Scripts:
	- These commands exist inside files create by the user and executing this file will execute the commands in it.
	- These files are also usually found /bin or /usr/bin although they can be stored anywhere.

Note: script != executable program (Shell Script is an 'ASCII text executable')

4. Aliases:
	- Aliases are used to make custom commands.
	- They make use of existing commands.
	- Even users can make/create aliases.

Ex: `ls` command is actually an alias command.

The `shell built-in` commands are the only ones out of the three NOT regarded as executables!.
The other three are `executables`.

### Finding the Type of a Command:

- `type commandName` = Gives you the type of the command. Type can differentiate btw aliases and built-in commands but NOT btween Executable and Shell Scripts -> it displays absolute path of the scripts/executables. Ex: 
- `type ls` = ls is aliased to `ls --color=auto'
- `type cd` = cd is a shell builtin

NOTE: To differentiate btween Executables and Shell scripts: We can do a `type` and then do `file` on the returned absolute path. This gives the type information of the file. Ex: 
- `type cp` = cp is /bin/cp
- `file /bin/cp` = Gives output: /bin/cp: ELF 64-bit LSB  executable, x86-64, version 1 (SYSV), dynamically linked (uses shared libs), for GNU/Linux 2.6.24, BuildID[sha1]=aac8232e6a5b347942f362c7a27cc3826de39073, stripped

- Executable Program = 'LSB executable'
- Shell Script = 'ASCII text executable'

Note: The files could be symbolic links/soft links to other files, which is what is mentioned when we run `type` and then `file` on the command and command file, respectively. So we have to run `file` on those files to gather info about the type of the command.

THEREFORE, COMMANDS CAN BE LINKS TO OTHER COMMANDS! - REMEMBER.

### Finding the Location of an Executable Command:

The `shell built-in` commands are the only ones out of the three NOT regarded as executables! The other three are executables.

- `which commandName` = Gives the location of an Executable command in the system (file path). Ex: `which cp` = /bin/cp

NOTE: `sbin` : Stands for `superuser binary`. Some executables are stored in the `sbin` folder also : Usually contains commands carried out by a system administrator such as networking commands, etc. Ex: `which reboot` = /sbin/reboot

NOTE: `which` does NOT display anything when used with Shell Built-ins. Ex: `which cd` = **Nothing/No output**. This is because shell built ins are NOT regarded as executables but are commands that are part of the shell itself. Hence, they don't have a path.

## Description/Information about Commands:

- `help commandName` = Gives information about 'SHELL BUILT-IN' commands ONLY!. (Does NOT work on executables. i.e: executable programs, shell scripts, aliases)

- `man commandName` = Opens a separate Screen displaying Info/Description about an executable command! ('man' stands for manual. Ex: how to use booklet) (Does not work on Shell Built-In commands)

USE `man` and `help` to learn about new commands you come across by yourself (since learning all the commands in a tutorial at once is impossible)

- `whatis commandName` = Displays/prints a very short description about the command(what it is and does) (Works only on Executables : Does NOT work on Shell Built-Ins)

Shell Built-In: use 'help' Executables(shell scripts, executable programs, aliases): 'man', 'whatis'

## Executing Multiple Commands:

**Method 1:**

We can execute multiple commands at once by separating them out with a `;`. Ex: 
- `ls;cal;date` = shows list of files/dirs in cwd THEN shows the calendar for current month THEN current date and time. (The order of commands matter)

This `;` method IGNORES (i.e shows command not found) all incorrect commands/typos and executes the correct commands! Ex: 
- `cal;ls;sfd` = ignores Cal(shows not found msg), prints list of files/dirs, ignores(shows not found msg) sfd.

Having an `exit` command in the `;` method will IGNORE the remaining commands on the line and Exit/End session.

**METHOD 2:** 

We can execute multiple commands at once by separating them out with a `&&`. Ex: 
- `ls && cal && date` = shows list of files/dirs in cwd THEN shows the calendar for current month THEN current date and time (The order of commands matter)

The difference btw the `;` and `&&` methods is that the `&&` follows 'Short circuiting' and will not execute after an incorrect/invalid command has been found. (Throws an error message for the incorrect command and stops)

## Wildcards: 

Used for matching file or directory names.

1. `*` : Matches Any Number of characters (Including 0 chars) Ex:
	- `rm *` : Removes EVERY file in the CWD.
	- `cp todo* dir1` : Copies every file STARTING with 'todo' to 'dir1' folder.
	- `cp *.txt dir1` : Copies every file ENDING with '.txt' to 'dir1' folder.(i.e every text file)
	- `cp *app* dir1` : Copies every file CONTAINING the word 'app' to 'dir1' folder.
	- `cp n*e dir1` : Copies every file STARTING WITH 'n' and ENDING WITH 'e' to 'dir1' folder.

2. `?` : Matches a Single Character. (One '?'' for Each Character required.) Ex:
	- `rm ?` : Removes all single character files from the CWD.
	- `cp file? dir1` : Copies all files such as file1, file2, filex, etc.. to dir1.
	- `cp file??.txt dir1` : Copes all files such as file42.txt, fileab.txt, etc.. to dir1. (One ? for each Char)

NOTE: We can COMBINE WILDCARDS: Ex: `cp f??e.* dir1` : Copies all files to dir1 that start with 'f' and end with 'e' with any 2 characters in between and then followed by a '.' and any number of characters(any extension).

3. `[]` : Specifying Ranges. Ex: 
	- `rm [abc]` : removes files named either 'a' or 'b' or 'c'.
	- `cp [abc]* dir1` : Copies all files to dir1 that begin with either 'a' or 'b' or 'c'.

NOTE: `!` inside the `[]` does the opposite of the command without the `!`: (COMPLEMENT). Ex:
- `cp [!abc]* dir1` : Copies all files to dir1 that DO NOT begin with either 'a' or 'b' or 'c'.

NOTE: `-` inside the `[]` represents a RANGE of characters. Ex:
- `cp [0-9]* dir1` : Copies all files to dir1 that begin with a number (0 to 9).
- `cp [0-6]* dir1` : Copies all files to dir1 that begin with a number between 0 and 6 (0 to 6 inclusive)

NOTE: `[:upper:]` inside a `[]` matches an Uppercase Character. Similarly:
- `[:lower:]` inside a `[]` matches an Lowercase Character.
- '[:digit:]' inside a `[]` matches an Digit.
- '[:alpha:]' inside a `[]` matches a Letter of the Alphabet.
- '[:alnum:]' inside a `[]` matches a Letter of the Alphabet/A Digit (matches an Alphanumeric character).
		
Ex:
- `rm [[:upper:]]*` : remove all files beginning with an uppercase character.
- `rm [[:lower:]]*` : remove all files beginning with an lowercase character.
- `rm *[[:digit:]]*` : remove all files containing a digit.
- `rm [![:digit:]]*` : remove all the files that do NOT begin with a digit.

## Aliases: 

Creating new command > Very Useful!

Syntax: `alias newCommandName="<whatever commands you want to execute...>"`

Ex:
- `alias invent="cd Desktop;mkdir newDir"` = The new `invent` command changes directory to Desktop and makes a new directory call newDir.

We can execute multiple commands on the same line by separating them with `;` therefore, we use it here in aliases.

How to check if command exists before creating new one? 
- Use the `type` command. If error/no output then command does not exist.

One use case for `aliases` would be that Windows users who work on linux can now create aliases with winodws command name that execute the corresponfing linux instructions.

### Deleting an Alias:

- `unalias aliasedCommandName` = running this will de-recognise the previously aliased command.


### The `~/.bashrc` file:

Used to permanently save aliases - for all sessions.

Setting aliases via the alias command on the terminal will not save them once the terminal session is logged out of/ended. That is, they are NOT Saved for the subsequent sessions.

In order to SAVE aliases permanently(for all subsequent sessions), we must ADD the alias command as a line to the `.bashrc` file inside the Home Directory. That is, Open .bashrc with:
- `cd ~`
- `vim .bashrc` 

(You need not use vim, can use any text editor, including GUI ones).

Add the alias command (Ex: `alias dir="ls"`) as a line inside the file and SAVE IT.

We must close the session and restart it for the alias to work. It will work for all subsequent sessions.

To Delete the permanent alias : Delete that alias's line from the `.bashrc` file inside your home directory.

NOTE:
- `alias` = Running the alias command WITHOUT ANY ARGUMENTS will print all the aliases that (have been created and) are in existence on the system. (Basically prints all the aliases that the system is using)
