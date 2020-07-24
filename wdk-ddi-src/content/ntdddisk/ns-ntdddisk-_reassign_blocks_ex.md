---
UID: NS:ntdddisk._REASSIGN_BLOCKS_EX
title: _REASSIGN_BLOCKS_EX (ntdddisk.h)
description: The REASSIGN_BLOCKS_EX structure is used in conjunction with the IOCTL_DISK_REASSIGN_BLOCKS_EX request to instruct a disk device to reassign the block numbers of the indicated bad blocks to good blocks.
old-location: storage\reassign_blocks_ex.htm
tech.root: storage
ms.assetid: D1BE17A0-39F1-496A-AD53-46A3F136D793
ms.date: 03/29/2018
keywords: ["_REASSIGN_BLOCKS_EX structure"]
ms.keywords: "*PREASSIGN_BLOCKS_EX, PREASSIGN_BLOCKS_EX, PREASSIGN_BLOCKS_EX structure pointer [Storage Devices], REASSIGN_BLOCKS_EX, REASSIGN_BLOCKS_EX structure [Storage Devices], _REASSIGN_BLOCKS_EX, ntdddisk/PREASSIGN_BLOCKS_EX, ntdddisk/REASSIGN_BLOCKS_EX, storage.reassign_blocks_ex"
f1_keywords:
 - "ntdddisk/REASSIGN_BLOCKS_EX"
 - "REASSIGN_BLOCKS_EX"
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
- ntdddisk.h
api_name:
- REASSIGN_BLOCKS_EX
targetos: Windows
req.typenames: REASSIGN_BLOCKS_EX, *PREASSIGN_BLOCKS_EX
---

# _REASSIGN_BLOCKS_EX structure


## -description


The <b>REASSIGN_BLOCKS_EX</b> structure is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_reassign_blocks_ex">IOCTL_DISK_REASSIGN_BLOCKS_EX</a> request to instruct a disk device to reassign the block numbers of the indicated bad blocks to good blocks.


## -struct-fields




### -field Reserved

Reserved for system use.


### -field Count

Contains the number of blocks in the array pointed to by <b>BlockNumber</b> to reassign.


### -field BlockNumber

Contains an array of block numbers corresponding to damaged blocks. These numbers will be reassigned to good blocks taken from the device's spare block pool.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_reassign_blocks_ex">IOCTL_DISK_REASSIGN_BLOCKS_EX</a>
 

 

