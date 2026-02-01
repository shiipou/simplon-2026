
## Introduction
---

Knowing basic Linux commands and how to navigate a terminal is a **core skill** for a developer. Many servers run without a graphical interface, making the command line the only way to interact with a system.

Understanding a small set of essential commands allows you to:

- Navigate the filesystem
- Manage files and directories
- Control permissions and ownership
- Interact with remote servers
- Monitor and manage running processes
- Troubleshoot systems efficiently

This cheat sheet focuses on the most commonly used core commands, with explanations, when to use them, important options, mnemonics, and practical examples.

## Table of Contents
---

- [Navigation](#navigation)
  - [`pwd`](#pwd)
  - [`ls`](#ls)
  - [`cd`](#cd)

- [Search & Documentation](#search--documentation)
  - [`man`](#man)
  - [`grep`](#grep)

- [File & Directory Management](#file--directory-management)
  - [`mkdir`](#mkdir)
  - [`touch`](#touch)
  - [`cp`](#cp)
  - [`mv`](#mv)
  - [`rm`](#rm)

- [Permissions & Ownership](#permissions--ownership)
  - [`sudo`](#sudo) 
  - [`chmod`](#chmod)
  - [`chown`](#chown)
  
- [Text Editors](#text-editors)
  - [`nano`](#nano)
  - [`vi`](#vi)

- [System & Process Management](#system--process-management)
  - [`top / htop`](#top--htop)
  - [`kill`](#kill)

- [Networking & Remote Access](#networking--remote-access)
  - [`ssh`](#ssh)
  - [`ping`](#ping)
  
- [Ressources](#Ressources)
---
## Navigation

---

### `pwd`
---

> [!info]- Mnemonic
> pwd stands for **P**rint **W**orking **D**irectory
#### Description

The `pwd` command is used to display the current working directory.

> [!example]
> 
>```bash
>pwd
>```


### `ls`
---

> [!info]- Mnemonic
> ls stands for **l**i**s**t
#### Description

The `ls` command is used to list the contents of a directory. It provides information about files and directories, such as their names, permissions, ownership, and more.

> [!important] Important options
> - `-l` : long format
> - `-a` : include hidden files
> - `-h` : human-readable sizes
> - `-r` : reverse order
> - `-R` : recursive

you can specify sevral options in one command by using all the letters corresponding to the options you want

> [!example]
> 
>```bash
>ls -lah
>```


### `cd`
---

> [!info]- **Mnemonic:**
>  cd means **C**hange **D**irectory
#### Description

The `cd` command is used to change the current working directory.

> [!example]
> - `cd ~` or `cd` : Changes the working directory to user's home directory
> - `cd ~username` : Changes the working directory to the specified user's home directory
> - `cd /` : Changes the working directory to the root directory
> - `cd ..` : Changes the working directory to the parent directory
> - `cd -` : Changes the working directory to the previous one
> - `cd directory name` : Changes the working directory to the specified child directory
> - `cd path/to/directory` : The path is appended to the working directory path, moving the context deeper into the directory tree hierarchy
> - `cd /full/path/to/directory` : The working directory is replaced with the specified absolute path
> 
> Special Symbols :
> 
> - `.` : References the actual directory
> - `..`: References the parent directory
> - `~` : Represents the home directory
> - `-` : Goes to the previous working directory

> [!tip]
> - Use `"Dir Name"` or `Dir\ Name` to deal with directories named with spaces
> - Use the `Tab` keystroke to auto-complete the directory names


---
## Search & Documentation

---

### `man`
---

 > [!info]- **Mnemonic:**
>  man stands for **Man**ual 
#### Description 

The `man` command is used to display any command documentation.

> [!example]
> ```bash
> man ls
> ```

> [!tip]
> Most commands also support the `--help` option for a quick summary of available options.
> 
> ```bash
> ls --help
> pwd --help
> ```


### `grep`
---
  
> [!info]- **Mnemonic:**
> grep stands for Global Regular Expression Print but you can remember it by thinking at **Grab** matching text
#### Description

The `grep` command is a powerful tool used for searching and matching patterns in text files.

> [!important] Important options
> - `-i` : ignore case
> - `-v` : search lines without the pattern
> - `-n` : adds the line number before each matching line
> - `-c` : count the lines
> - `-r` : recursive
> - `-l` : display only the name of the filer where the pattern matches

> [!example]
> ```bash
> grep "ERROR" app.log
> grep -ri "password" .
> ``````


---
## File & Directory Management

---

### `mkdir`
---
  
> [!info]- Mnemonic
> mkdir stands for **M**a**k**e **Dir**ectory

#### Description

The `mkdir` command is used to create new directories. You can create a single directory or multiple directories at once.

> [!important] Important options
> - `-p` create parent directories\

> [!example]
> ```bash
> mkdir logs
> mkdir -p projects/linux/basics
> ```


### `touch`
---
#### Description 

The `touch` command is a versatile tool used to create new files or update the timestamps of existing files.

> [!important] Important options
> - `-a`: Updates the access time of the file.
> - `-m`: Updates the modification time of the file.
> - `-d` or `-t`: Sets the access and modification times to the specified date and time.
> - `-c` or `-f`: Creates the file if it doesn't exist, without issuing an error message.
  
> [!example]
> ```bash
> touch -m file.txt
> ```


### `cp`
---
  
> [!info]- Mnemonic
> cp stands for **C**o**p**y
#### Description

The `cp` command is used to copy files and directories from one location to another.

> [!important] Important options
> - `-r` recursive copy
> - `-v` verbose

> [!example]
> ```bash
> cp file.txt backup.txt
> cp -rv src/ backup_src/
> ```


### `mv`
---
  
> [!info]- Mnemonic
> mv stands for **m**o**v**e
#### Description

The `mv` command is used to move or rename files and directories.

> [!important] Important options
> - `-i`: Interactive mode, prompts before overwriting
> - `-f`: Force mode, overwrites without prompting
> - `-v`: Verbose mode, shows the details of the move operation


> [!example]
> ```bash
> mv old.txt new.txt
> mv file.txt /tmp/
> ```


### `rm`
---
  
> [!info]- Mnemonic
> rm stands for **r**emo**v**e

> [!caution]
> Deletion is permanent.
#### Description

The `rm` command is a powerful tool, but it should be used with caution as it permanently deletes files and directories without the ability to recover them.

> [!important] Important options
> - `-f`: Force removal of files and directories without prompting for confirmation.
> - `-r`: Recursively remove directories and their contents.
> - `-i`: Prompt for confirmation before removing each file or directory.


> [!example]
> ```bash
> rm file1.txt file2.txt
> rm -rf build/
> ```


---
## Permissions & Ownership

---

### `sudo`
---

> [!info]- Mnemonic
> sudo stands for **su**per user **do**
#### Description

The `sudo` command is essential for system administration tasks, as it allows users to perform actions that require elevated permissions, such as installing software, modifying system configurations, or accessing protected resources.

> [!example]
> ```bash
> sudo apt update
> sudo rm /protected/file
> ```


### `chmod`
---

> [!info]- Mnemonic
> **ch**ange **mod**e
#### Context

In Linux, each file and directory has three main permission categories:

1. **Owner**: The user who created the file or directory.
2. **Group**: The group that the owner belongs to.
3. **Others**: All other users on the system.

Each of these categories has three permission types:

1. **Read (r)**: Allows the user to view the contents of the file or list the files in a directory.
2. **Write (w)**: Allows the user to modify the contents of the file or create/delete files in a directory.
3. **Execute (x)**: Allows the user to run the file as a program or access the contents of a directory.

You can view the permissions of a file or directory using the `ls -l` command. The output will show the permissions in the following format:

```bash
-rw-r--r-- 1 labex labex 0 Apr 24 12:34 example.txt
```

The first 10 characters represent the file permissions:

- The first character indicates the file type (`-` for regular file, `d` for directory).
- The next 3 characters represent the owner's permissions.
- The next 3 characters represent the group's permissions.
- The final 3 characters represent the permissions for others.
#### Description

The `chmod` command allows you to modify the read, write, and execute permissions for the owner, group, and others.

> [!summary] The 2 modes
> - Symbolic mode :
> 	- `u` represents the owner
> 	- `g` represents the group
> 	- `o` represents others
> 	- `a` represents all (owner, group, and others)
> 	- `+` adds the specified permissions
> 	- `-` removes the specified permissions
> 	- `=` sets the specified permissions
>- Numeric mode :
> 	- Each permission (read, write, execute) is assigned a number: 4 for read, 2 for write, and 1 for execute.
> 	- The permissions for owner, group, and others are represented by a 3-digit number.
> 

> [!example]
> ```bash
> chmod 755 example.txt
> chmod +x example.txt
> chmod u=rw,g=r,o-rwx example.txt
> ```


### `chown`
---

> [!info]- Mnemonic
> chown stands for **ch**ange **own**er
#### Description

The `chown` command is used to change the owner and group owner of a file.

> [!example]
> ```bash
> sudo chown user file.txt
> sudo chown user:group file.txt
> ```


---
## Text Editors

---

### `nano`
---
#### Description:

The `nano` command will open the nano editor, which is a beginner-friendly terminal text editor.

> [!summary] Common shortcuts
> - `Ctrl + O` save
> - `Ctrl + X` exit  

> [!example]
> ```bash
> nano file.txt
> ```


### `vi`
---
#### Description

The `vi` command will open the vi editor, which is a powerful modal text editor available on almost all Unix systems.

> [!summary] Basic commands
> - `Esc` : command mode
> 	- `:wq` : save and quit
> 	- `:q!` : quit without saving
> 	- `arrows` : move the cursor or `h` to move the cursor left, `j` to move down, `k` to move up, and `l` to move right
> 	- `w` : move the cursor to the beginning of the next word
> 	- `b` : move the cursor to the beginning of the previous word.
> 	- `0` : move the cursor to the beginning of the current line
> 	- `$` : move the cursor to the end of the current line.
>- `i` : insert mode
> 	- `x` : delete the character under the cursor.
> 	- `dd` : delete the entire line.
> 	- `yy` : copy the current line.
> 	- `p` : paste the copied text.
> 

> [!example]
> ```bash
> vi file.txt
> ```


---
## System & Process Management
 ---
  
### `top` / `htop`
---

> [!info]- Mnemonic
> top shows what’s on **top** of the system

#### Description

The `top` command displays various system information, including:

- Uptime: The time since the system was last booted.
- Tasks: The total number of running, sleeping, stopped, and zombie processes.
- CPU utilization: The percentage of CPU time spent in user mode, system mode, nice mode, idle, waiting, hardware interrupts, and software interrupts.
- Memory usage: The total, free, used, and buffered/cached memory.
- Swap usage: The total, free, and used swap space.
- Process list: A list of the most resource-intensive processes, sorted by CPU or memory usage.

```
top - 10:28:53 up 40 min,  1 user,  load average: 0.00, 0.00, 0.00
Tasks:  23 total,   1 running,  22 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.1 sy,  0.0 ni, 99.9 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :  15993.2 total,  15549.3 free,    500.9 used,    135.9 buff/cache
MiB Swap:   4096.0 total,   4096.0 free,      0.0 used.  15492.3 avail Mem
``
    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
      1 root      20   0   21656  12628   9428 S   0.0   0.1   0:01.57 systemd
      2 root      20   0    3120   1920   1920 S   0.0   0.0   0:00.01 init-systemd(Ub
      6 root      20   0    3120   1792   1792 S   0.0   0.0   0:00.00 init
     44 root      19  -1   50352  15744  14848 S   0.0   0.1   0:00.45 systemd-journal
     98 root      20   0   25532   6784   4992 S   0.0   0.0   0:00.14 systemd-udevd
    107 systemd+  20   0   21456  12672  10624 S   0.0   0.1   0:00.13 systemd-resolve
    108 systemd+  20   0   91024   7808   6912 S   0.0   0.0   0:00.11 systemd-timesyn
    155 root      20   0    4236   2560   2432 S   0.0   0.0   0:00.01 cron
    156 message+  20   0    9648   4992   4480 S   0.0   0.0   0:00.13 dbus-daemon
    178 root      20   0   17960   8192   7424 S   0.0   0.1   0:00.09 systemd-logind
    181 root      20   0 1755840  12672  10624 S   0.0   0.1   0:00.34 wsl-pro-service
    187 root      20   0    3160   2048   1920 S   0.0   0.0   0:00.01 agetty
    202 syslog    20   0  222508   5632   4480 S   0.0   0.0   0:00.11 rsyslogd
    211 root      20   0    3116   1920   1792 S   0.0   0.0   0:00.00 agetty

```

> [!important] Important option
> - `-h`: Display the help menu
> - `-1`: Toggle between per-CPU and aggregate CPU utilization
> - `-f`: Manage the columns displayed
> - `-o`: Customize the sort order
> - `-u`: Filter processes by a specific user

When top displays a static list that is refreshed periodically, htop offers a modern interactive experience. You can navigate with the arrow keys or mouse, filter in real time, sort by any column, and act directly on processes without leaving the interface.

<u>htop vs top: why is htop better?</u>

**Visual navigation:**
instead of typing commands, you navigate with the arrow keys and perform actions with the function keys Meaningful colors: each color has a meaning (green = user process, red = kernel, blue = low priority).

**Instant filtering:**
type F4 then a name, and only the corresponding processes are displayed. Group actions: select several processes with the Space bar, then kill them all at once with F9.

**Please note:**
While top is installed by default on any machine, htop is not. You will need to use two commands to install it:

> [!todo] Installing htop
> ```bash
> sudo apt update
> sudo apt install htop
> ```

> [!example]
> ```bash
> top
> htop
> ````


### `kill`
---

> [!info]- Mnemonic
> kill is used to **kill** a process
#### Description

The `kill` command is used to terminate or send signals to running processes. To stop a process, you need to type eather it's name or it's binary name.

> [!important] Important option
> - `-9` force kill

> [!example]
> ```bash
> kill 5339436
> kill -9 firefox
> ```


---
## Networking & Remote Access

---

### `ssh`
---

> [!info]- Mnemonic
> ssh stands for **s**ecure **sh**ell
#### Description

The `ssh` command is used to connect to a remote linux servers securely and transfer files between local and remote hosts.

> [!tip]
> To exit the SSH session, type `exit` and press Enter.

> [!example]
> ```bash
> ssh user@ip_adress
> ssh user@domain_name
> ```


### `ping`
---
#### Description

The `ping` command is a network diagnostic tool used to test the connectivity between a local host and a remote host. It sends Internet Control Message Protocol (ICMP) echo request packets to the target host and waits for the ICMP echo reply.
  
> [!example]
> ```bash
> ping google.com
> ```


---
## Ressources

---

Here is a link to a website which includes a cheat sheet for linux commands https://linux-commands.labex.io