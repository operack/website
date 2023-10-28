---
title: "How-to: VMware Increase Disk Size and Resize an Ubuntu LVM Partition"
author: mdomocos
date: 2023-10-28 15:00:00 +0200
categories: [Linux, VMware]
tags: [ubuntu, linux, vmware]
---

## Introduction
Logical Volume Management (LVM) is a versatile disk management tool used in many Linux distributions, including Ubuntu. In this guide, we'll explore how to expand a VMware virtual machine's disk and subsequently increase an Ubuntu LVM partition.

## Prerequisites

- A VMware virtual machine with Ubuntu installed and configured with LVM.
- VMware vSphere or VMware Workstation.
- Backup of the virtual machine (always essential before modifying disk structures).

## Steps to Increase Disk Size in VMware

1. **Power off the Virtual Machine**: Ensure the VM is powered off before you begin.
2. **Open VMware vSphere or Workstation**: Navigate to the VM's settings.
3. **Locate the Hard Disk you want to expand**: In the `Hardware` tab, select the disk you wish to enlarge.
4. **Increase Disk Size**: Specify the new desired size and confirm the change.
5. **Power on the Virtual Machine**: Start up the VM after adjusting the disk size.

## Resizing the Ubuntu LVM Partition

With the VMware VM disk expanded, the next step involves resizing the Ubuntu LVM partition to use the new space.

1. **Log into Ubuntu**: Access the terminal.
2. **Check Physical Volume**:
   ```bash
   sudo pvdisplay
   ```
3. **Expand the Physical Volume**:
   ```bash
    sudo pvresize /dev/sdaX
   ```
3. **Expand the Physical Volume**:
   ```bash
   sudo pvresize /dev/sdaX
   ```
   Replace `sdaX` with the appropriate disk identifier from the `pvdisplay` output.
4. **Check Volume Group**:
   ```bash
   sudo vgdisplay
   ```
5. **Expand the Logical Volume**:
   ```bash
   sudo lvresize -l +100%FREE /dev/ubuntu-vg/ubuntu-lv
   ```
   Ensure you replace `/dev/ubuntu-vg/ubuntu-lv` with your logical volume path, if different.
6. **Resize the File System**:
   ```bash
   sudo resize2fs /dev/ubuntu-vg/ubuntu-lv
   ```
   Remember to replace the logical volume path if yours differs from the default.

## Conclusion

You've now successfully enlarged your VMware VM disk and resized the Ubuntu LVM partition to make use of the additional space. Always back up your data and configurations before modifying disk structures, ensuring data integrity and easy recovery if needed.
