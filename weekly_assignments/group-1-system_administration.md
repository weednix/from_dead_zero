Group 1: Linux System Administration
====================================

Four topics in this group:

- disk partitioning and filesystems
- doing backups
- system performance statistics (sar)
- finding things

here's some other ideas for topics we can choose from:

- the /proc filesystem
- systemd and the init system
- boot managers
- package manager
- regular expressions (grep, awk, sed)




disk partitioning and filesystems
---------------------------------

### 1) What is a filesystem?

focusing on the ext2 filesystem, be able to explain the following stuff:

- blocks
- block groups
- superblocks
- inodes
- directories
- symbolic links

resources:

- https://www.kernel.org/doc/html/latest/filesystems/ext2.html
- https://www.nongnu.org/ext2-doc/ext2.html

this second resource gets very detailed.  just read through the topics and skim over
data types and vars


### 2) partition a disk device

prereqs: 

-  we each need a ec2 instance with extra ebs volume to practice on
-  or at least an empty usb drive (take care)

tasks:

- answer the following:

  - what is a block device?
  - what is a partition table?
  - what is a master boot record?

- print out initial partition state
- create at lease two partitions of various sizes
- print out final partition state

Commands to use:

``` 
  parted
  fdisk
```

Choose from one of these to create your partitions, but read about both and be
able to use both to print out partition table

resources:

- http://gnu.ist.utl.pt/software/parted/manual/parted.html


### 3) create and mount a filesystem

prereqs: 
  an unformatted partition on some disk device

tasks:

- Create an ext2 filesystem 
- mount the filesystem on `/mnt`
- make some directories and files in this new filesystem
- list what you created

commands:

- mkfs.ext2
- mount
- mkdir
- touch


### 4) recovering a bad filesystem

tasks:

- unmount your filesystem
- use `dd` command to overwrite your primary superblock
- try to remount
- use `fsck` to repair the filesystem
- remount and list dirs/files



.
.
.
.


system performance statistics
-----------------------------

resources:

- https://tldp.org/LDP/tlk/mm/memory.html
- https://notes.eddyerburgh.me/operating-systems/linux/process-scheduling
- http://www.linfo.org/kernel_topics_index.html

  - http://www.linfo.org/kernel.html
  - http://www.linfo.org/process.html
  - http://www.linfo.org/pid.html
  - http://www.linfo.org/process_state.html
  - http://www.linfo.org/multitasking.html
  - http://www.linfo.org/kernel_mode.html
  - http://www.linfo.org/user_mode.html
  - http://www.linfo.org/system_call.html
  - http://www.linfo.org/context_switch.html
  - http://www.linfo.org/software_interrupt.html
  - http://www.linfo.org/kernel_space.html
  - http://www.linfo.org/user_space.html

read man pages for the following commands:

- free
- vmstat
- iostat
- ps
- top
- sar

be able to explain concepts:

- process table:

  - pid
  - uid
  - priority
  - nice
  - state
  - running process
  - sleeping process
  - blocked process
  - run queue
  - interrupts
  - context switching

- cpu:

  - user vs. system
  - i/o wait
  - idle
  - load average

- memory

  - used
  - free
  - cached
  - bufferred
  - swapped
  - available
  - shared
  - virtual set size vs. resident set size
  - paging
  - page reclaimation efficiency (sar %vmeff)

- i/o:

  - blocks read/write per second
  - requests per second
  - average queue size/length
  - avarage wait time





doing backups
-------------

learn commands:

- rsync
- tar

write a shell script to perform daily incremental backup to a external usb device

write a shell script to perform daily incremental backup to S3 bucket

links:

This article gets very specific about shell scripting.  it's nice:
https://linuxhint.com/inotofy-rsync-bash-live-backups/

https://linuxconfig.org/how-to-create-incremental-backups-using-rsync-on-linux







finding things
--------------

