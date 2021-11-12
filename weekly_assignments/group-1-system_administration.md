Group 1: Linux System Administration
====================================

Four topics in this group:

- disk partitioning and filesystems
- system performance statistics (sar)
- finding things
- regular expressions (grep, awk, sed)

here's some other ideas for topics we can choose from:

- doing backups
- the /proc filesystem
- systemd and the init system
- boot managers
- package manager




disk partitioning and filesystems
---------------------------------

+++1) What is a filesystem?

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


+++2) partition a disk device

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


+++3) create and mount a filesystem

prereqs: 
  an unformatted partition on some disk device

tasks:

- Create an ext2 filesystem 
- mount the filesystem on `/mnt`
- make some directories and files in this new filesystem
- list what you created

commands::

  mkfs.ext2
  mount
  mkdir
  touch


+++4) recovering a bad filesystem

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


system performance statistics (sar)
-----------------------------------

finding things
--------------

regular expressions (grep, awk, sed)
------------------------------------