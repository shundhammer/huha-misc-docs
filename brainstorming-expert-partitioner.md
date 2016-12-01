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



## YaST Expert Partitioner

Compared with everything else on the market (including Windows and MacOS), the
YaST expert partitioner is the most powerful tool by far.

### Available Views

- <Hostname>
  - Hard Disks
  - RAID
  - Volume Management
  - Crypt Files
  - Device Mapper
  - NFS
  - Btrfs
  - tmpfs
  - Unused Devices
- Device Graph
- Mount Graph
- Installation Summary
- Settings


### New Features

Already requested:

- Create filesystem on disk directly without partition table

- Create LUKS on disk directly


Not requested yet, but forseeable:

- Btrfs as volume manager (Btrfs spanning multiple partitions, very much like
  LVM)


### Ideas

#### Subvolumes Directly Below a Btrfs Partition

Right now, subvolumes are very much hidden: You only see them in the
"installation summary" (proposal) view. Otherwise you'll have to click on a
Btrfs partition and then "Edit" and then on the "subvolumes" volume.

### Hyperlinks in Many Views

Whenever a view is HTML-like (not a table with selectable items), add
hyperlinks at appropriate places.

Example:

    Partition: /dev/vda3

      Device:

        Device: /dev/vda3
        Size: 40 GiB
        Encrypted: No
        Device Path:
        Device ID 1:
        FS ID: 0x83 Linux native
        File System:

    File System:

        File System: Ext4
        Mount Point: /home
        Label: Home

- Size: Same as "Resize" button
- Encrypted: Toggle encryption
- FS ID: Change partition type / ID
- File System: Change filesystem type / format flag
- Mount point: Edit mount point
- Label: Edit partition label

etc.

In other cases (if a partition is used by LVM), jump to the appropriate view
(LVM in this case).

In the table-like views, context menus serve very much the same purpose
already.

In an ideal world, we'd present only the item a user clicked on - only the
partition label, only the encryption flag etc; for a first version, we'd open
the appropriate "edit partition" (etc.) dialog where the user can change other
things as well.

The problem is that some of those settings are interdependent of each other;
that would raise usability problems in some cases. For example, changing either
the partition type or the mount point of a swap partition would also imply to
change the other, and that is realistically only possible (and usable) if the
user sees them both at the same time.

_**To be discussed**_


### Guided Workflows for Complex Tasks (RAID, LVM)
