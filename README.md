# Local LVM Lifecycle Manager (RHEL 9 Edition)

![License](https://img.shields.io/badge/License-MIT-green.svg)
![Platform](https://img.shields.io/badge/Platform-RHEL%209%20%7C%20Rocky%20Linux-orange.svg)

This is an automated LVM management script designed to simplify logical volume lifecycle operations in enterprise Linux environments. This project is not only a practical tool, but also a deep hands-on implementation of core storage concepts from the **RHCSA (Red Hat Certified System Administrator)** certification.

## 🚀 Key Features
- **Intelligent Scenario Detection**: Automatically identifies the state of the target path using `findmnt` and `lsblk`.
- **Force Cleanup Mechanism**: Integrates `wipefs` and lazy unmount (Lazy Umount) to resolve `device or resource busy` errors.
- **Online Capacity Expansion**: Supports non-disruptive, online resizing for both XFS and EXT4 file systems.
- **Robust Handling**: Locks metadata before disk signature cleanup to prevent logical chain breakage.

## 🎓 RHCSA Coverage
This script implements the following key RHCSA exam and real-world administration concepts:

1. **Physical Volume (PV) Management**  
   Handles residual signatures and force-initializes physical devices.

2. **Volume Group (VG) Management**  
   Creates new volume groups and dynamically extends existing ones (`vgextend`).

3. **Logical Volume (LV) Management**  
   Allocates space on demand and resizes volumes using `lvextend`.

4. **Filesystem Operations**  
   Manages differences between XFS (`xfs_growfs`) and EXT4 (`resize2fs`) during expansion.

5. **Troubleshooting & Device Handling**  
   Resolves common production issues such as mounted partitions and device conflicts.

## 🛠️ Quick Start
```bash
chmod +x lvm_std_extend.sh
sudo ./lvm_std_extend.sh
