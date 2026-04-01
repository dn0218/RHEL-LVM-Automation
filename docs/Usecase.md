# LVM Management Use Case Report

This document provides a detailed walkthrough of testing the script across four real-world scenarios, along with low-level technical explanations and command analysis.

---

## 🔧 Environment Setup

Before running the script, the following test environment was prepared:

```bash
[danny@rhel ~]$ lsblk
NAME          MAJ:MIN RM  SIZE RO TYPE MOUNTPOINTS
sda             8:0    0    5G  0 disk 
sdb             8:16   0    5G  0 disk 
sdc             8:32   0    5G  0 disk 
sr0            11:0    1 12.7G  0 rom  /run/media/danny/RHEL-9-7-0-BaseOS-x86_64
nvme0n1       259:0    0   20G  0 disk 
├─nvme0n1p1   259:1    0  600M  0 part /boot/efi
├─nvme0n1p2   259:2    0    1G  0 part /boot
└─nvme0n1p3   259:3    0 18.4G  0 part 
  ├─rhel-root 253:0    0 16.4G  0 lvm  /
  └─rhel-swap 253:1    0    2G  0 lvm  [SWAP]
[danny@rhel ~]$ sudo mkdir -p /mnt/data1
[danny@rhel ~]$ sudo mkdir -p /mnt/data2
[danny@rhel ~]$ sudo mkdir -p /mnt/data3
```  
  Mount points:  
  /mnt/data1  
  /mnt/data2  
  /mnt/data3  
