# **2 - Booting and System Management Daemons**

Consists of a few broadly defined tasks:

- finding, loading, and running bootstrapping code
- finding, loading, and running the OS kernel
- running startup scripts and system daemons
- maintaining process hygiene and managing system state transitions

## 2.1 - Boot Process Overview

Most Linux distributions now use a system manager daemon called **systemd** 

- streamlines the boot process by adding dependency management
- support for concurrent startup processes
- comprehensive approach to logging

During bootstrapping, the kernel is loaded into memory and executed

- admins have little direct control over most booting step

Filesystems are checked and mounted before system is fully booted

- managed by shell scripts run by **init** or parsed by **systemd**

## 2.2 - System Firmware

CPU executed boot code in ROM when system is turned on

Can control exposure of devices to the OS through the firmware

During a normal bootstrapping the system firmware 

- probes for hardware and disks
- run health checks
- looks for bootstrapping code

To boot from a particular drive, set the selected drive as the highest priority and make sure "hard disk" is enabled as boot medium

### BIOS vs UEFI

**Basic Input/Output System (BIOS)** - traditional PC firmware

**Unified Extensible Firmware Interface (UEFI)** - modern version of BIOS 

### Legacy BIOS

assumes the boot device starts with the Master Boot Record (MPR)

- includes the first-stage boot loader and a primitive disk partitioning table
- boot loader space < 512 bytes

second-stage boot loader live in the dead zone between MBR and beginning of the first disk partition

- knows about the OS and filesystems 
- can configure options on its own

### UEFI

Uses the modern GUID Partitioning Table (GPT) to partition hard disks

Understands File Allocation Table (FAT) filesystems 

During boot, GPT is consulted by the firmware to identify the EFI System Partition (ESP)

No need for a boot-loader

- target can be a UNIX or Linux kernel that has been configured for direct UEFI loading

## Boot Loaders

Main job is to identify and load an appropriate OS kernel

Marshals the configuration arguments for a kernel 

- kernels don't have a command line

## GRUB: The GRand Unified Boot Loader

Default boot loader on most Linux distributions

GRUB 2 is the modern version of GRUB, GRUB Legacy is the older version

### GRUB configuration

Lets you specify parameters and the operating mode to boot into

Can understand filesystems and find its way to the root

Configurations are located in **/etc/default/grub**

- run **update-grub** if changes are made to the file

### The GRUB command line

typing c at the GRUB boot screen will allow access to its command line

- holding SHIFT while booting computer will lead to the GRUB boot screen

### 









