# **1 - Where to Start**

## 1.1 - Essential Duties of a System Administrator

Controlling access - creates, removes, and handles all accounts 

Adding hardware - install and configure OS (adding a network card, configuring specialized external storage array)

Automating tasks - using tools to automate repetitive and time-consuming tasks

Overseeing backups - backing up and restoring data when required

Installing and upgrading software - select, install, and configure software on a variety of OS

Monitoring - detecting and fixing failures 

Troubleshooting - finding the source of a problem and resolving it

Maintaining local documentation - keeping documentations so others knows what's going on

Vigilantly monitoring security - protecting network-attacked systems

Tuning performance - investigate sever operations and identify the problem

Developing site policies - help develop sensible policies that meet the letter and intent of the law 

Working with vendors- selecting and vendors, assisting with contract negotiations, and implementing solutions

## 1.2 - Suggested Background

Learning and mastering **vi** 

Learn **expect**

## 1.3 - Linux Distributions

Comprehensive list of Linux distributions can be found at lwn.net/Distributions

## 1.7 - Man Pages and Other Online Documentation

Concise descriptions of individual commands, drivers, file formats, or library routines

### Organization of man pages

**man** finds the appropriate page wherever it is stored 

Shows what section a search belongs to (1-9)

1. User-level commands and applications
2. System calls and kernel error codes
3. Library calls
4. Device drivers and network protocols
5. Standard file formats
6. Games and demonstrations
7. Miscellaneous files and documents
8. System admin commands
9. Obscure kernel specs and interfaces

### man: read man pages

**man** ***title*** formats a specific manual page and sends it to you terminal through **more**, **less**

**man** ***section title*** shows the section man page of the keyword title

**man -k** ***keyword*** prints a list of man pages with the keyword in it 

- **apropos** ***keyword*** does the same thing

### Storage of man pages

**nroff** input for man pages is stored in **/usr/share/man** and compressed with **gzip** to save space

- man knows how o decompress them on the fly
- **nroff** formats documents for TTY devices (virtual terminals tty1 -> tty63)

**manpath** reveals the search path for **man**

## 1.10 - Ways to Find and Install Software

Modern OS are divided into packages that can be installed independently from one another

- only install what is needed

Most add-on software is provided in the form of precompiled packages developed by independents and picked up by package repositories that format it to the correct conventions

Two systems using the same package format does not mean two systems are interchangeable

### Determining if software is installed

**which** command locates a given command

^ can't find the command, use **whereis**

**locate** command can find any type of file

- updated periodically by the **updatedb** command

Use the command **dpkg-query** to find out which package a file belongs to

### Adding new software 

`sudo apt-get install tcpdump` will install the tcpdump package 

