---
UID: NE:ufs.__unnamed_enum_2
title: UFS_PURGE_STATUS (ufs.h)
description: Specifies the current status of a purge operation.
old-location: storage\ufs_purge_status.htm
tech.root: storage
ms.assetid: 9BC978A9-FA5E-4A1E-9775-1DC9C270F5DC
ms.date: 03/29/2018
ms.keywords: UFS_PURGE_STATUS, UFS_PURGE_STATUS enumeration [Storage Devices], UFS_PurgeStatusFailure, UFS_PurgeStatusIdle, UFS_PurgeStatusInProgress, UFS_PurgeStatusInterrupted, UFS_PurgeStatusQueueNotEmpty, UFS_PurgeStatusSuccess, storage.ufs_purge_status, ufs/UFS_PURGE_STATUS, ufs/UFS_PurgeStatusFailure, ufs/UFS_PurgeStatusIdle, ufs/UFS_PurgeStatusInProgress, ufs/UFS_PurgeStatusInterrupted, ufs/UFS_PurgeStatusQueueNotEmpty, ufs/UFS_PurgeStatusSuccess
ms.topic: enum
req.header: ufs.h
req.include-header: 
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
- Ufs.h
api_name:
- UFS_PURGE_STATUS
product:
- Windows
targetos: Windows
req.typenames: UFS_PURGE_STATUS
---

# UFS_PURGE_STATUS enumeration


## -description


Specifies the current status of a purge operation.


## -enum-fields




### -field UFS_PurgeStatusIdle

The status of the purge operation has already been read but was not returned.


### -field UFS_PurgeStatusInProgress

The purge operation is currently in progress.


### -field UFS_PurgeStatusInterrupted

The current purge operation was interrupted.


### -field UFS_PurgeStatusSuccess

The current purge operation was successful.


### -field UFS_PurgeStatusQueueNotEmpty

The current purge operation failed due to the logical queue being not empty.


### -field UFS_PurgeStatusFailure

The current purge operation failed.


## -remarks



When the <b>UFS_PURGE_STATUS</b> is equal to
the values 2, 3, 4, or 5, the
<b>UFS_PURGE_STATUS</b> is automatically
cleared to <b>UFS_PurgeStatusIdle</b> the first time
that it is read.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ufs/ne-ufs-ufs_attributes_descriptor">UFS_ATTRIBUTES_DESCRIPTOR</a>
 

 

