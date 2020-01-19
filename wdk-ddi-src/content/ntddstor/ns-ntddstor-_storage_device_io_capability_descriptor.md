---
UID: NS:ntddstor._STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR
title: _STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR (ntddstor.h)
description: The output buffer for the StorageDeviceIoCapabilityProperty as defined in STORAGE_PROPERTY_ID.
old-location: storage\storage_device_io_capability_descriptor.htm
tech.root: storage
ms.assetid: 98377F8F-62C8-4E8F-838B-A63DC63E4A0C
ms.date: 03/29/2018
ms.keywords: PSTORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR, PSTORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR structure pointer [Storage Devices], STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR, STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR structure [Storage Devices], _STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR, ntddstor/PSTORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR, ntddstor/STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR, storage.storage_device_io_capability_descriptor
ms.topic: struct
f1_keywords:
 - "ntddstor/STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR"
req.header: ntddstor.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- ntddstor.h
api_name:
- STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR, PSTORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR
---

# _STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR structure


## -description


The output buffer for the StorageDeviceIoCapabilityProperty as defined in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ne-ntddstor-storage_property_id">STORAGE_PROPERTY_ID</a>.


## -struct-fields




### -field Version

The version of this structure. The Size serves as the version.


### -field Size

The size of this structure.


### -field LunMaxIoCount

The logical unit number (LUN) max outstanding I/O count.


### -field AdapterMaxIoCount

The adapter max outstanding I/O count.

