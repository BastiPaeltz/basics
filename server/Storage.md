# Storage

## add a disk - linux recipe

* **sude fdisk -l**
* create **partition for new drive** --> **gparted**
* put drive's space into "unformated" partition
* create mountpoint before mounting
* always verify identiy of disks (**best use UUID's**)
* **look up online tutorials**

## software side of storage

* partitioning inferior to LVM 
* **RAID**: combines multiple storage devies into one virtualized device
* **LVM** - volume groups - physical devies form pools of storage 
* **filesystem**: mediates between raw bag of blocks presented by partition, RAID or logical volums and the standard filesystem interface expected by programs
* determines how and where files are stored
* **LVM is the future**
* **secure erase** done in Linux with **hdparm**
* syntax : **hdparm [options] device** --> way to read and write the firmware of hard disks
* **smartmontools** monitors hard drive and offers **smartctl** command for interactive queries or scripting

## RAID

* mirroring and parity schemes
* important RAID levels: **0, 1, 5, 6**
* linux software raid **mdadm** command


## LVM

* read tutorials
* complicated
* :(

## Filesystems

* **journaling** - changes are written to journal first and then committed into the filesystem
* files where the parent dir cant be determined are thrown in **lost+found**
* verify size of filesystem with **df** command
* special chapter about **ZFS** - UNix handbook p.264+
*    
