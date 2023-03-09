# SSH & SCP Notes/Reference:

- [SSH & SCP Notes/Reference:](#ssh---scp-notes-reference-)
  * [Secure Shell (SSH):](#secure-shell--ssh--)
    + [Connecting:](#connecting-)
  * [Secure Copying (SCP):](#secure-copying--scp--)
    + [Coyping from Remote to Local:](#coyping-from-remote-to-local-)
    + [Coyping from Local to Remote:](#coyping-from-local-to-remote-)

## Secure Shell (SSH):

### Connecting:

- `ssh userName@remoteHostAddress` = Connects to remote host via SSH. (Ex: `ssh tester@add1sun.com`)

If requiring port address:
- `ssh -pXXXX userName@remoteHostAddress` = connects to remote using port number XXXX. (Ex: `ssh -p1234 tester@add1sun.com`)

**Use lowercase 'p' for port Number**

Once you login, you may use basic linux commands to move around the directories or manipulate files on the remote system.

## Secure Copying (SCP):

Syntax:
- `scp [options] [portNumber] sourceHostFileOrDirectoryPath destinationDirectoryPath`

NOTE: Use Uppercase 'P' for port number flag (In SSH, we used lowercase 'p').

### Coyping from Remote to Local:

1. Copying a File: `scp -PXXXX userName@remoteHostAddress:filePath localDirectoryPath`
2. Copying a Directory: `scp -r -PXXXX userName@remoteHostAddress:directoryPath localDirectoryPath`

Use `-r` flag : Recursively copies directory contents.

### Coyping from Local to Remote:

1. Copying a File: `scp -PXXXX localDirectoryPath userName@remoteHostAddress:directoryPath`
2. Copying a Directory: `scp -r -PXXXX localDirectoryPath userName@remoteHostAddress:directoryPath`

Use `-r` flag : Recursively copies directory contents.
