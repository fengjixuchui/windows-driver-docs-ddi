---
UID: NS:ntddtape._TAPE_SET_POSITION
title: _TAPE_SET_POSITION (ntddtape.h)
description: The TAPE_SET_POSITION structure is used in conjunction with the IOCTL_TAPE_SET_POSITION request to move the current position on the tape to the specified partition and offset.
old-location: storage\tape_set_position.htm
tech.root: storage
ms.assetid: c9f462b2-4b56-4138-a374-9e9d3e1ae295
ms.date: 03/29/2018
keywords: ["TAPE_SET_POSITION structure"]
ms.keywords: "*PTAPE_SET_POSITION, PTAPE_SET_POSITION, PTAPE_SET_POSITION structure pointer [Storage Devices], TAPE_SET_POSITION, TAPE_SET_POSITION structure [Storage Devices], _TAPE_SET_POSITION, ntddtape/PTAPE_SET_POSITION, ntddtape/TAPE_SET_POSITION, storage.tape_set_position, structs-tape_412b4b85-a0b5-4372-a32c-fa7ac5a6f33a.xml"
req.header: ntddtape.h
req.include-header: Ntddtape.h, Minitape.h
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
targetos: Windows
req.typenames: TAPE_SET_POSITION, *PTAPE_SET_POSITION
f1_keywords:
 - _TAPE_SET_POSITION
 - ntddtape/_TAPE_SET_POSITION
 - PTAPE_SET_POSITION
 - ntddtape/PTAPE_SET_POSITION
 - TAPE_SET_POSITION
 - ntddtape/TAPE_SET_POSITION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddtape.h
api_name:
 - TAPE_SET_POSITION
---

# _TAPE_SET_POSITION structure (ntddtape.h)


## -description

The TAPE_SET_POSITION structure is used in conjunction with the <a href="/windows-hardware/drivers/ddi/ntddtape/ni-ntddtape-ioctl_tape_set_position">IOCTL_TAPE_SET_POSITION</a> request to move the current position on the tape to the specified partition and offset.

## -struct-fields

### -field Method

Indicates the type of positioning to perform. This member must have one of the following values:





#### TAPE_REWIND

Positions the tape at the beginning of the partition indicated in <b>Partition</b> if the media is partitioned, and to the beginning of the media if the media is not partitioned. If the media is not partitioned, <b>Partition</b> must be set to zero. The <b>Offset</b> member is ignored. 



#### TAPE_ABSOLUTE_BLOCK

Positions the tape at the absolute block address located at the offset from the beginning specified by <b>Offset</b>. The value in the <b>Partition</b> member is ignored. 



#### TAPE_LOGICAL_BLOCK

Positions the tape to the logical block address specified by <b>Offset</b>, relative to the beginning of the partition indicated in <b>Partition</b>. If the media is not partitioned, <b>Partition</b> must be set to zero. 



#### TAPE_PSEUDO_LOGICAL_BLOCK

Positions the tape to the pseudological block address specified by <b>Offset</b>, relative to the beginning of the partition indicated in <b>Partition</b>. If the media is not partitioned, <b>Partition</b> must be to zero.



#### TAPE_SPACE_END_OF_DATA

Positions the tape at the end of the partition indicated in <b>Partition</b>, or if the media is not partitioned, at the end of the tape. The <b>Offset</b> member is ignored. 



#### TAPE_SPACE_RELATIVE_BLOCKS

Starting from the current position, positions the tape immediately after the number of blocks specified by <b>Offset</b>. The <b>Partition</b> member is ignored. 



#### TAPE_SPACE_FILEMARKS

Starting from the current position, positions the tape immediately after the number of filemarks specified by <b>Offset</b>. The <b>Partition</b> member is ignored. 



#### TAPE_SPACE_SEQUENTIAL_FMKS

Starting from the current position, positions the tape immediately after the next occurrence, if any, of the number of consecutive filemarks specified by <b>Offset</b>. The <b>Partition</b> member is ignored. 



#### TAPE_SPACE_SETMARKS

Starting from the current position, positions the tape immediately after the number of setmarks specified by <b>Offset</b>. The <b>Partition</b> member is ignored. 



#### TAPE_SPACE_SEQUENTIAL_SMKS

Starting from the current position, positions the tape immediately after the next occurrence, if any, of the number of consecutive setmarks specified by <b>Offset</b>. The <b>Partition</b> member is ignored.

### -field Partition

Indicates the partition in which to set the tape's position. This member must have one of the following values:


<dl>
<dt>NOT_PARTITIONED (or zero)</dt>
<dt>DATA_PARTITION</dt>
<dt>DIRECTORY_PARTITION</dt>
</dl>


If the media is not partitioned, this member is zero.

### -field Offset

Specifies an offset whose type depends on the value in <b>Method</b>. If the specified method positions the tape to a block address, <b>Offset</b> specifies the byte offset into the specified partition. If the specified method is to skip blocks, filemarks, or setmarks, <b>Offset</b> specifies the number to skip. If <b>Offset</b> is zero, the tape is positioned at the beginning of the partition.

### -field Immediate

When set to <b>TRUE</b>, indicates that the target device should return status immediately. When set to <b>FALSE</b>, indicates that the device should return status after the operation is complete. 


##### - Method.TAPE_ABSOLUTE_BLOCK

Positions the tape at the absolute block address located at the offset from the beginning specified by <b>Offset</b>. The value in the <b>Partition</b> member is ignored. 


##### - Method.TAPE_LOGICAL_BLOCK

Positions the tape to the logical block address specified by <b>Offset</b>, relative to the beginning of the partition indicated in <b>Partition</b>. If the media is not partitioned, <b>Partition</b> must be set to zero. 


##### - Method.TAPE_PSEUDO_LOGICAL_BLOCK

Positions the tape to the pseudological block address specified by <b>Offset</b>, relative to the beginning of the partition indicated in <b>Partition</b>. If the media is not partitioned, <b>Partition</b> must be to zero.


##### - Method.TAPE_REWIND

Positions the tape at the beginning of the partition indicated in <b>Partition</b> if the media is partitioned, and to the beginning of the media if the media is not partitioned. If the media is not partitioned, <b>Partition</b> must be set to zero. The <b>Offset</b> member is ignored. 


##### - Method.TAPE_SPACE_END_OF_DATA

Positions the tape at the end of the partition indicated in <b>Partition</b>, or if the media is not partitioned, at the end of the tape. The <b>Offset</b> member is ignored. 


##### - Method.TAPE_SPACE_FILEMARKS

Starting from the current position, positions the tape immediately after the number of filemarks specified by <b>Offset</b>. The <b>Partition</b> member is ignored. 


##### - Method.TAPE_SPACE_RELATIVE_BLOCKS

Starting from the current position, positions the tape immediately after the number of blocks specified by <b>Offset</b>. The <b>Partition</b> member is ignored. 


##### - Method.TAPE_SPACE_SEQUENTIAL_FMKS

Starting from the current position, positions the tape immediately after the next occurrence, if any, of the number of consecutive filemarks specified by <b>Offset</b>. The <b>Partition</b> member is ignored. 


##### - Method.TAPE_SPACE_SEQUENTIAL_SMKS

Starting from the current position, positions the tape immediately after the next occurrence, if any, of the number of consecutive setmarks specified by <b>Offset</b>. The <b>Partition</b> member is ignored. 


##### - Method.TAPE_SPACE_SETMARKS

Starting from the current position, positions the tape immediately after the number of setmarks specified by <b>Offset</b>. The <b>Partition</b> member is ignored.

## -remarks

Note that a drive or a tape may not support all <b>Method</b> values.

Partitions are numbered logically from 1 to N. However, a partition number does not imply a physical position on the tape. For example, partition number one might not be at the beginning of the media.

When the offset specifies a number of blocks, filemarks, or setmarks to position over, a positive value N in the offset causes forward positioning over N blocks, filemarks, or setmarks, halting on the end-of-partition or end-of-tape side of the block, filemark, or setmark. A zero value in the offset causes no change of position. A negative value N in the offset causes reverse positioning, toward the beginning of the partition or the tape media, over N blocks, filemarks, or setmarks, halting on the beginning-of-partition side of a block, filemark, or setmark.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddtape/ni-ntddtape-ioctl_tape_set_position">IOCTL_TAPE_SET_POSITION</a>



<a href="/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniSetPosition</a>