# Expert Partitioner Brainstorming

## Existing GUI Partitioning Tools for Linux


None of the tools in this section offer anything beyond very basic
partition-based operations. In particular,

- no LVM

- no RAID

- no encryption (LUKS etc.)


### GParted

https://en.wikipedia.org/wiki/GParted

![screenshot](https://upload.wikimedia.org/wikipedia/commons/2/2c/GParted_0.18_GUID_partition_table.png)



### QtParted

https://en.wikipedia.org/wiki/QtParted

![screenshot](https://upload.wikimedia.org/wikipedia/commons/f/ff/Qtparted_screenshot.png)



### KDE partition manager
  https://en.wikipedia.org/wiki/KDE_Partition_Manager

  ![screenshot](https://upload.wikimedia.org/wikipedia/commons/a/af/KDE_Partition_Manager_screenshot.jpg



### GNOME disks (gnome-disk-utility

https://en.wikipedia.org/wiki/GNOME_Disks

![screenshot](https://upload.wikimedia.org/wikipedia/commons/c/cd/GNOME_Disks_3.12.1.png)



## Other Graphical Storage Related Tools for Linux/Unix


### PartedMagic

https://partedmagic.com/

This is little more than a Linux ISO that boots into a desktop with GParted.


### Logical Volume Management (Ubuntu / Red Hat)

https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/6/html/Storage_Administration_Guide/s1-system-config-lvm.html


![screenshot](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/6/html/Storage_Administration_Guide/images/lvm-main1.png)

![screenshot](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/6/html/Storage_Administration_Guide/images/lvm-main2.png)

![screenshot](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/6/html/Storage_Administration_Guide/images/lvm-main3.png)

- only LVM, nothing else (no partition management)

- tree based like our expert partitioner

- graphical display: cylinders for logical volumes and physical volumes

- tree branch "uninitialized entities"

- all operations largely based on dialogs with input fields, combo boxes and
  sometimes sliders


### Solaris Volume Manager

http://shrubbery.net/solaris9ab/SUNWaadm/LOGVOLMGRADMIN/p6.html

http://docs.oracle.com/cd/E19253-01/816-4520/

![screenshot](http://docs.oracle.com/cd/E18752_01/html/816-4520/figures/svm-gui.png)
http://docs.oracle.com/cd/E18752_01/html/816-4520/exlwh.html


This tool looks quite promising at first glance, but it's just one huge device
tree starting at "this computer" with a lot of branches that are mostly just
very loosely related to each other.





## New Features

- Create filesystem on disk directly without partition table

- Create LUKS on disk directly

