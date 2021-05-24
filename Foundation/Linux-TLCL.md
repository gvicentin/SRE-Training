# Linux

My annotations for the book The Linux Command Line (TLCL second edition). The commands were runned in an AWS EC2 instance, using Ubuntu Server.


## What is the Shell

The **Shell** is a program that can take user input and passes the commands to the operational system. Bash stands for *"Bourne Again SHell"* and it is an enchaced shell. Other types of shell are *zsh* or *fish*.

The first view of the shell looks something like this. It's showing the username and the hostname separated by an @. The next thing it shows is the working direcotry. `~` means the user home directory. If the last character is `#` the shell is running with *superuser* privileges, `$` is used otherwise.

```bash
[username@hostname ~]$
```

**date** command shows the current date and time.
```bash
$ date
Sat May 22 20:11:27 UTC 2021
```

**cal** command shows a calendar tool
```bash
$ cal
      May 2021
Su Mo Tu We Th Fr Sa
                   1
 2  3  4  5  6  7  8
 9 10 11 12 13 14 15
16 17 18 19 20 21 22
23 24 25 26 27 28 29
30 31
```

**df** show the current amount of free space on the disk partitions
```bash
$ df
Filesystem     1K-blocks    Used Available Use% Mounted on
/dev/root       10098432 1494484   8587564  15% /
devtmpfs          495236       0    495236   0% /dev
tmpfs             501024       0    501024   0% /dev/shm
tmpfs             100208     780     99428   1% /run
tmpfs               5120       0      5120   0% /run/lock
tmpfs             501024       0    501024   0% /sys/fs/cgroup
/dev/loop0         34176   34176         0 100% /snap/amazon-ssm-agent/3552
/dev/loop1         56832   56832         0 100% /snap/core18/1997
/dev/loop2         72192   72192         0 100% /snap/lxd/19647
/dev/loop3         33152   33152         0 100% /snap/snapd/11588
/dev/loop4         56832   56832         0 100% /snap/core18/2066
/dev/loop5         32896   32896         0 100% /snap/snapd/11841
/dev/loop6         69248   69248         0 100% /snap/lxd/20326
tmpfs             100204       0    100204   0% /run/user/1000
```

**free** command is used to see free space on the memory
```bash
$ free
              total        used        free      shared  buff/cache   available
Mem:        1002052      167108       75084         780      759860      641648
Swap:             0           0           0
```

We can end our terminal session with the command `exit`.

We usually run the shell in a terminal emulator, but we use the *virtual terminal* or *virtual consoles*.  If using an graphical environment we can access the virtual terminals with shortscuts like Crtl+F1-F6.


## Navegation

Linux organize its files on a tree structures (has always only one) using the pattaerns of `directories`. Storage devices are `mounted` at various points of the tree.

### Current working directory

Use `pwd` to print the current working directory.

### Listing the content of a directory

```bash
$ ls /
bin   dev  home  lib32  libx32      media  opt   root  sbin  srv  tmp  var
boot  etc  lib   lib64  lost+found  mnt    proc  run   snap  sys  usr
```

### Changin the working directory

* **Absolute path**: An absolute path always begins in the root directory (using the `/` in the first character). 
* **Relative path**: An relative path is assumend when starting with the `.` (can be omitted) or `..`.

**Which one to use?? The one that needs less typing!!!**

| Shortcuts | Result |
| ----------|--------|
| cd | Change workdir to home of the current user directory |
| cd - | Change workdir to the last used directory | 
| cd ~*username* | Change workdir to the `username` home directory | 


### Obs:
1. Hidden files begin with `.`. We list them using list all command: `ls -a` 
2. Filenames are case sensitive.
3. Linux has no concept of file extensions. But some applications do.
4. Do not use spaces in the filenames!
   

## Explotring the System

Commands in GNU/Linux follow the structure showed bellow. Usually, the options can be expressed by an dash (`-`) followed by a single letter, for abreviation, or by a double dash (`-`) with the option name.

```bash
command -options arguments
```

### Useful Options for `ls` command
| Option | Long Option| Description |
|-|-|-|
| `-a` | `--all`| List all files, including the hidden ones |
| `-A` | `--almost-all` | Similar to the above, but dosent print `.` and `..` |
| `d` | `--directory` |  Use this option along with `-l` to see the details about the directory rather than its content |
| `-F` | `--classify` | Append an indicator to the end of the file | 
| `-h` | `--human-readable` | Show the file sizes in human readable form | 
| `-l` | | Display long format |
| `-r` | `--reverse` | Display the list in the reverse order. Usually ls displays the content in alphabetic order |
| `-S` | | Sort by file size |
| `-t` | | Sort by modification time | 

### Long listing fields

```bash
$ ls -l
-rw-r--r-- 1 ubuntu ubuntu   44 May 22 01:44 hello_script.sh
drwxrwxr-x 2 ubuntu ubuntu 4096 May 22 22:00 work
```

1. **-rw-r--r--**: Access permissions to the file. The letter indicates the type of the file (Among other `-` is for files and `d` is for directories). The next are the (read, write, execute) for the user, group, and other.
2. **1**: Quantity of hard links.
3. **ubuntu**: The file owner.
4. **ubuntu**: The group wich owns the file.
5. **44**: File size.
6. **May 22 01:44**: Date and time of the last modification.
7. **hello_script.sh**: Name of the file.

### File

Use the command `file` to know what type is a file.
```bash
$ file TLCL-13.07.pdf
TLCL-13.07.pdf: PDF document, version 1.4
```

### Less

We can view large text files with command `less`.

Command when using the less program.
| Command | Action | 
|-|-|
| G | Moves to end of the file |
| 1G or g | Moves to beggining of the file |
| /*characters* | Search for *characters* |
| n | Go tho the next occurrence |
| h | Shows the help screen | 
| q | quit the program |

### Linux Filesystem Hierarchy Standart


 