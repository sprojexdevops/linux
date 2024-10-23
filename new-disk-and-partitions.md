## After adding new disk, mount the partitions to it
> 'fdisk' is a command line utility
### check the storage devices attached to the server
    fdisk -l

* For example, there are 2 disks
    1. /dev/sda - default or exsisting
    2. /dev/sdb - newly attached

### Manage the storage device
    fdisk <device name>

> eg: fdisk /dev/sdb

enter into the command line for fdisk
> 'm' for help

Command (m for help): m

#### _Help_:

##### DOS (MBR)
    a   toggle a bootable flag
    b   edit nested BSD disklabel
    c   toggle the dos compatibility flag

##### Generic
    d   delete a partition
    F   list free unpartitioned space
    l   list known partition types
    n   add a new partition
    p   print the partition table
    t   change a partition type
    v   verify the partition table
    i   print information about a partition

##### Misc
    m   print this menu
    u   change display/entry units
    x   extra functionality (experts only)

##### Script
    I   load disk layout from sfdisk script file
    O   dump disk layout to sfdisk script file

##### Save & Exit
    w   write table to disk and exit
    q   quit without saving changes

##### Create a new label
    g   create a new empty GPT partition table
    G   create a new empty SGI (IRIX) partition table
    o   create a new empty DOS partition table
    s   create a new empty Sun partition table


### After creating the partitions in new disk, inform the OS about the changes
    partprode <device name>

> eg: partprobe /dev/sdb