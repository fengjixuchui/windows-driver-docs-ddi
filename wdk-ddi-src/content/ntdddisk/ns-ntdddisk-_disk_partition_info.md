---
UID: NS:ntdddisk._DISK_PARTITION_INFO
title: _DISK_PARTITION_INFO (ntdddisk.h)
description: The DISK_PARTITION_INFO structure is used to report information about the disk's partition table.
old-location: storage\disk_partition_info.htm
tech.root: storage
ms.assetid: 14df0604-39cd-4743-a051-894d63f4417c
ms.date: 03/29/2018
keywords: ["_DISK_PARTITION_INFO structure"]
ms.keywords: "*PDISK_PARTITION_INFO, DISK_PARTITION_INFO, DISK_PARTITION_INFO structure [Storage Devices], PDISK_PARTITION_INFO, PDISK_PARTITION_INFO structure pointer [Storage Devices], _DISK_PARTITION_INFO, ntdddisk/DISK_PARTITION_INFO, ntdddisk/PDISK_PARTITION_INFO, storage.disk_partition_info, structs-disk_307cbbb9-2940-4a87-b6b7-04e588811b8e.xml"
f1_keywords:
 - "ntdddisk/DISK_PARTITION_INFO"
 - "DISK_PARTITION_INFO"
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
- ntdddisk.h
api_name:
- DISK_PARTITION_INFO
targetos: Windows
req.typenames: DISK_PARTITION_INFO, *PDISK_PARTITION_INFO
---

# _DISK_PARTITION_INFO structure


## -description


The <b>DISK_PARTITION_INFO</b> structure is used to report information about the disk's partition table. 


## -struct-fields




### -field SizeOfPartitionInfo

Size of this structure in bytes. Set to <b>sizeof</b>(DISK_PARTITION_INFO).


### -field PartitionStyle

Takes a <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff563773(v=vs.85)">PARTITION_STYLE</a> enumerated value that specifies the type of partition table the disk contains.


### -field DUMMYUNIONNAME

 


### -field DUMMYUNIONNAME.Mbr

If <b>PartitionStyle</b> == MBR


### -field DUMMYUNIONNAME.Mbr.Signature

Specifies the signature value, which uniquely identifies the disk. The <b>Mbr</b> member of the union is used to specify the disk signature data for a disk formatted with a Master Boot Record (MBR) format partition table. Any other value indicates that the partition is not a boot partition. This member is valid when <b>PartitionStyle</b> is <b>PARTITION_STYLE_MBR</b>. 


### -field DUMMYUNIONNAME.Mbr.CheckSum

Specifies the checksum for the master boot record. The <b>Mbr</b> member of the union is used to specify the disk signature data for a disk formatted with a Master Boot Record (MBR) format partition table. This member is valid when <b>PartitionStyle</b> is <b>PARTITION_STYLE_MBR</b>. 


### -field DUMMYUNIONNAME.Gpt

If <b>PartitionStyle</b> == GPT


### -field DUMMYUNIONNAME.Gpt.DiskId

Specifies the GUID that uniquely identifies the disk. The <b>Gpt</b> member of the union is used to specify the disk signature data for a disk that is formatted with a GUID Partition Table (GPT) format partition table. This member is valid when <b>PartitionStyle</b> is <b>PARTITION_STYLE_GPT</b>. The GUID data type is described on the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-guids-in-drivers">Using GUIDs in Drivers</a> reference page.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_disk_geometry_ex">DISK_GEOMETRY_EX</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff563773(v=vs.85)">PARTITION_STYLE</a>
 

 

