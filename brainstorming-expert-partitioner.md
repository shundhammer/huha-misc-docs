# Expert Partitioner Brainstorming

## Existing Graphical Partitioning Tools for Linux

- gparted

- qtparted

- KDE partition manager

- GNOME disk utility


None of the above offer anything beyond very basic partition-based operations:

- no LVM

- no RAID

- no encryption (LUKS etc.)


## Other Graphical Storage Related Tools for Linux/Unix


### PartedMagic

https://partedmagic.com/

This is little more than a Linux ISO that boots into a desktop with GParted.


### Logical Volume Management (Ubuntu / Red Hat)

https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/6/html/Storage_Administration_Guide/s1-system-config-lvm.html

- only LVM, nothing else (no partition management)

- tree based like our expert partitioner

- graphical display: cylinders for logical volumes and physical volumes

- tree branch "uninitialized entities"

- all operations largely based on dialogs with input fields, combo boxes and
  sometimes sliders


### Solaris Volume Manager

http://shrubbery.net/solaris9ab/SUNWaadm/LOGVOLMGRADMIN/p6.html

http://docs.oracle.com/cd/E19253-01/816-4520/

This tool looks quite promising at first glance, but it's just one huge device
tree starting at "this computer" with a lot of branches that are mostly just
very loosely related to each other.

http://docs.oracle.com/cd/E18752_01/html/816-4520/exlwh.html





## New Features

- Create filesystem on disk directly without partition table

- Create LUKS on disk directly

