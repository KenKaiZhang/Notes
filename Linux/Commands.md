# **Commands**

**vi** : standard text editor standard on all OS

**vimtutor**: introduction on how to use vi

**man**: concise descriptions of individual commands, drivers, file formats, or library routines

- **man** ***title*** formats a specific manual page and sends it to you terminal through **more**, **less***
- **man** ***section title*** shows the section man page of the keyword title
- **man -k** ***keyword*** prints a list of man pages with the keyword in it 
  - **apropos** ***keyword*** does the same thing

**mandb**: updates the manual page 

**manpath**: reveals the search path for **man**

##Locating Files

**which**: find out where a command is locatedsudo systemc

**wheris**: which but has a broader search 

**locate**: find files by name (even broader and more detailed)


## Pacakage Management

**dpkg-query**: find out which package a file belongs to

**apt-get**: used to handle APT packages

- **apt-get install** ***package*** installs a package
- **apt-get upgrade** ***package*** updates package to the latest version

**dpkg** - package handling command for Debian and Ubuntu systems

- **dpkg -l** shows all packages installed on the system
- **dpkg --install** to install new packages


## System Control
**systemctl** - investigate the status of **systemd** and configure it 

- **systemctl list-units** is the default is the command runs by itself; shows all the active unit files with the (.suffix)
- **systemctl list-units** ***unit*** shows all active unit files with the keyword suffix
- **systemctl list-unit-file** shows all unit files regardless of activity
- **sudo systemctl** ***option*** **-l** ***unit*** shows details on the condition of an unit file
  - Options:
    - **enable** enables unit to activate at boot
    - **disable** prevents unit from activating at boot
    - **isolate** changes operating mode to target
    - **start** activates unit immediately
    - **stop** deactivates unit immediately
    - **restart** restarts unit immediately
    - **status** shows unit's status and recent log entries
    - **kill** sends a signal to units 
- **sudo systemctl reboot** reboots the computer
- **sudo systemctl daemon-reload** reloads unit files and **systemd** configurations
- **sudo systemctl isolate** ***target*** change the current operating mode


## Journals
**journalctl** - displays all log entries

- **journalctl --list-boots** shows list of prior boots
  - **journalctl -b** ***long-form ID*** shows the journal content of a specific boot
- **journalctl -u** shows logs related to a specific unit 
- **journalctl -f** shows the logs as they come in 

--

**ls -l** - used to see ownership of files

**su** - a good way to access the root account (keeps a log entry showing who became root and when)

- **su** ***-username*** allows access to account

**sudo** - takes in arguments and executes it as root (keeps log of the commands executed)

##Signals
**Signals to know**:

- HUP - hangup
- INT - interrupt
- QUIT
- KILL
- BUS - Bus error
- SEGV - segmentation fault
- TERM - software termination
- STOP
- TSTP - keyboard stop
- CONT - continue after stop
- WINCH - window change
- USR1
- USR2

**kill** - terminates a process without sending it a TERM signal

- **kill -l** lists all signals 
- **kill** ***PID*** kills a process with the PID
- **kill -9 **guarantees that a process will be terminated

**killall** - kills all processes with name

**sudo pkill** - searches for process by name and sends the specific signal

- **sudo pkill -u** ***username*** - kills all process running under username

##Process
**ps** - monitoring process

- **ps aux** shows ALL processes
- **ps lax** same as ^ but more technical aux

**pidof** ***process name*** - shows the PID of a process

- can run with path of process 

**pgrep** ***process name*** - shows the PID of a process

- only with name

**top** - a real time version of ps

--

**crontab** - maintains crontab for users (kept in /var/spool/cron/crontabs)

- **-e** to edit crontabs
- **-l** to list crontabs

**mount** - attaching filesystems to the tree (shows the mounted filesystems)

- **umount** does the opposite of mount

**file** - shows information on a certain file

--

**ls** - lists contents of a directory

- **ls -ld** shows information for a directory
- **ls -b** shows control characters as octal
- **ls -h** shows file size in readable way
- **ls -t** sorts file by time created

**rm** - tool for deleting files

- **rm --** tells rm that everything after -- is a file name
- **rm -i** checks with user if they want to delete the file before deleting it

**ln** ***oldfile newfile*** - creates a hard link  (syntax same as cp command)

- **ln -s** creates a soft link 

**chmod** - changes the permission on a file

- can utilize octal or mnemonic syntax
- octal:
  - 0 = ---
  - 1 = --x
  - 2 = -w-
  - 3 = -wx
  - 4 = r--
  - 5 = r-x
  - 6 = rw-
  - 7 = rwx

**chown *new_owner file*** - changes a file's ownership

**chgrp *new_group_owner file*** - changes a file's group ownership

- both can use the **-R** flag to change ownership of all files underneath

**umask** - influence the default permissions given to a created file

- octal values are the reverse of chmod

##APT

**apt** - the Advanced Package Tool is one of the most mature package management system

- **apt update** before running **apt install** to get new version
- **sudo apt update && apt upgrade -y** - used to install and upgrade packages in system
  - **-y** skips the confirmation
- **sudo apt autoremove** - removes unused packages in the system
- **apt show *package_name*** - shows info on the package

##New User
**chfn** - allows users to change GECOS field (name, office number, work phone, home phone)

**usermod** - to set settings for a certain user

- many flags to determine what in the /etc/shadow file to edit for a user

**sudo useradd** - adds a user to the system

**sudo passwd *newusername*** - assigns a password to the new user

## Linux Volume Management
**pvs** - shows all the physicl volumes

- **pvcreat** creates pv
- **pvdisplay** inspects pv
- **pvchange** modifies pv
- **pvck** checks pv

**vgs** - shows the volume groups

- **vgcreate** creates vg
- **vgchange** modifies vg
- **vgextend** extends vg
- **vgdisplay** inspects vg
- **vgck** checks vg
- **vgscan** enables vg


**lvs** - shows the logical volumes

- **lvcreate** creates lv
- **lvchange** modifies lv
- **lvresize** resize lv
- **lvdisplay** inspects lv




























