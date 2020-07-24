---
UID: NI:ntdddisk.IOCTL_DISK_DELETE_DRIVE_LAYOUT
title: IOCTL_DISK_DELETE_DRIVE_LAYOUT (ntdddisk.h)
description: Removes partition information from the disk.
old-location: storage\ioctl_disk_delete_drive_layout.htm
tech.root: storage
ms.assetid: 787fa1ce-5305-4159-8710-3c6971133c4c
ms.date: 03/29/2018
keywords: ["IOCTL_DISK_DELETE_DRIVE_LAYOUT IOCTL"]
ms.keywords: IOCTL_DISK_DELETE_DRIVE_LAYOUT, IOCTL_DISK_DELETE_DRIVE_LAYOUT control, IOCTL_DISK_DELETE_DRIVE_LAYOUT control code [Storage Devices], k307_7319c33d-d8ab-438c-9908-ac380bff54b5.xml, ntdddisk/IOCTL_DISK_DELETE_DRIVE_LAYOUT, storage.ioctl_disk_delete_drive_layout
f1_keywords:
 - "ntdddisk/IOCTL_DISK_DELETE_DRIVE_LAYOUT"
 - "IOCTL_DISK_DELETE_DRIVE_LAYOUT"
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntdddisk.h
api_name:
- IOCTL_DISK_DELETE_DRIVE_LAYOUT
targetos: Windows
req.typenames: 
---

# IOCTL_DISK_DELETE_DRIVE_LAYOUT IOCTL


## -description



Removes partition information from the disk. If the partition style of the disk is Master Boot Record (MBR), sector 0 of the disk is wiped clean except for the bootstrap code. All signatures, such as the AA55 boot signature and the NTFT disk signature, will be removed. If the partition style of the disk is GUID Partition Table (GPT), the primary partition table header in sector 1 and the backup partition table in the last sector of the disk are wiped clean. This operation can be used to generate so-called "superfloppies" that contain a file system starting at the first sector of the disk rather than in a partition on the disk.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES.

