---
UID: NS:ntddvol._VOLUME_PHYSICAL_OFFSETS
title: _VOLUME_PHYSICAL_OFFSETS (ntddvol.h)
description: The VOLUME_PHYSICAL_OFFSETS structure contains an array of physical offsets and accompanying physical disk numbers and is used with IOCTL_VOLUME_LOGICAL_TO_PHYSICAL to request a series of pairs of physical offsets and disk numbers that correspond to a single logical offset.
old-location: storage\volume_physical_offsets.htm
tech.root: storage
ms.assetid: 876cb283-ce0d-44ed-b515-d4ee31089b88
ms.date: 03/29/2018
keywords: ["_VOLUME_PHYSICAL_OFFSETS structure"]
ms.keywords: "*PVOLUME_PHYSICAL_OFFSETS, PVOLUME_PHYSICAL_OFFSETS, PVOLUME_PHYSICAL_OFFSETS structure pointer [Storage Devices], VOLUME_PHYSICAL_OFFSETS, VOLUME_PHYSICAL_OFFSETS structure [Storage Devices], _VOLUME_PHYSICAL_OFFSETS, ntddvol/PVOLUME_PHYSICAL_OFFSETS, ntddvol/VOLUME_PHYSICAL_OFFSETS, storage.volume_physical_offsets, structs-volumemgr_f5ee82b1-a42a-47aa-a3fd-116eeb3b441b.xml"
f1_keywords:
 - "ntddvol/VOLUME_PHYSICAL_OFFSETS"
req.header: ntddvol.h
req.include-header: Ntddvol.h
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
- ntddvol.h
api_name:
- VOLUME_PHYSICAL_OFFSETS
product:
- Windows
targetos: Windows
req.typenames: VOLUME_PHYSICAL_OFFSETS, *PVOLUME_PHYSICAL_OFFSETS
---

# _VOLUME_PHYSICAL_OFFSETS structure


## -description


The VOLUME_PHYSICAL_OFFSETS structure contains an array of physical offsets and accompanying physical disk numbers and is used with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ni-ntddvol-ioctl_volume_logical_to_physical">IOCTL_VOLUME_LOGICAL_TO_PHYSICAL</a> to request a series of pairs of physical offsets and disk numbers that correspond to a single logical offset. 


## -struct-fields




### -field NumberOfPhysicalOffsets

Contains the number of physical offsets returned by the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ni-ntddvol-ioctl_volume_logical_to_physical">IOCTL_VOLUME_LOGICAL_TO_PHYSICAL</a>. 


### -field PhysicalOffset

Contains an array of structures of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ns-ntddvol-_volume_physical_offset">VOLUME_PHYSICAL_OFFSET</a>. Each element of the array contains a pair consisting of a physical disk number and an accompanying physical offset <disk number, disk offset>. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ni-ntddvol-ioctl_volume_logical_to_physical">IOCTL_VOLUME_LOGICAL_TO_PHYSICAL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ni-ntddvol-ioctl_volume_physical_to_logical">IOCTL_VOLUME_PHYSICAL_TO_LOGICAL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvol/ns-ntddvol-_volume_physical_offset">VOLUME_PHYSICAL_OFFSET</a>
 

 

