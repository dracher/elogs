title: LVM Thinpool NGN And More
thumbnail: /img/blog.png
categories: Technical
date: 2016-04-06 14:05:19
tags: [lvm, ngn]
---

## Terms


- `JBOD` Just a Bunch Of Disks
- `LVM` Logical Volume Manager
- `meta devices` provide an abstraction layer between a file system and the physical storage that is used underneath

## LVM organizes storage in three different levels

- hard drives, partitions, RAID systems or other means of storage are initialized as physical volumes (PVs)
- Physical Volumes (PV) are grouped together in Volume Groups (VG)
- Logical Volumes (LV) are managed in Volume Groups (VG)
