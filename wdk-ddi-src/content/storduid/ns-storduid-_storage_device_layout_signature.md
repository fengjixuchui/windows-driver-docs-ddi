---
UID: NS:storduid._STORAGE_DEVICE_LAYOUT_SIGNATURE
title: _STORAGE_DEVICE_LAYOUT_SIGNATURE (storduid.h)
description: The STORAGE_DEVICE_LAYOUT_SIGNATURE structure defines a device layout structure.
old-location: storage\storage_device_layout_signature.htm
tech.root: storage
ms.assetid: 3c433fe5-1782-4a00-aa7b-1558b0f56080
ms.date: 03/29/2018
keywords: ["_STORAGE_DEVICE_LAYOUT_SIGNATURE structure"]
ms.keywords: "*PSTORAGE_DEVICE_LAYOUT_SIGNATURE, PSTORAGE_DEVICE_LAYOUT_SIGNATURE, PSTORAGE_DEVICE_LAYOUT_SIGNATURE structure pointer [Storage Devices], STORAGE_DEVICE_LAYOUT_SIGNATURE, STORAGE_DEVICE_LAYOUT_SIGNATURE structure [Storage Devices], _STORAGE_DEVICE_LAYOUT_SIGNATURE, storage.storage_device_layout_signature, storduid/PSTORAGE_DEVICE_LAYOUT_SIGNATURE, storduid/STORAGE_DEVICE_LAYOUT_SIGNATURE, structs-general_0392587a-aab6-4f49-bb7e-3ebf8acc87bb.xml"
f1_keywords:
 - "storduid/STORAGE_DEVICE_LAYOUT_SIGNATURE"
 - "STORAGE_DEVICE_LAYOUT_SIGNATURE"
req.header: storduid.h
req.include-header: Storduid.h
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
- storduid.h
api_name:
- STORAGE_DEVICE_LAYOUT_SIGNATURE
targetos: Windows
req.typenames: STORAGE_DEVICE_LAYOUT_SIGNATURE, *PSTORAGE_DEVICE_LAYOUT_SIGNATURE
---

# _STORAGE_DEVICE_LAYOUT_SIGNATURE structure


## -description


The STORAGE_DEVICE_LAYOUT_SIGNATURE structure defines a device layout structure.


## -struct-fields




### -field Version

The version of the DUID.


### -field Size

The size, in bytes, of this STORAGE_DEVICE_LAYOUT_SIGNATURE structure.


### -field Mbr

A Boolean value that indicates whether the partition table of the disk is formatted with a master boot record (MBR). If <b>TRUE</b>, the partition table of the disk is formatted with a master boot record (MBR). If <b>FALSE</b>, the disk has a GUID partition table (GPT).


### -field DeviceSpecific


### -field DeviceSpecific.MbrSignature

The signature value, which uniquely identifies the disk.


### -field DeviceSpecific.GptDiskId

The GUID that uniquely identifies the disk.


## -remarks



The device layout signature contributes to the definition of a device unique identifier (DUID). For more information about DUIDs, see the description of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storduid/ns-storduid-_storage_device_unique_identifier">STORAGE_DEVICE_UNIQUE_IDENTIFIER</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storduid/ns-storduid-_storage_device_unique_identifier">STORAGE_DEVICE_UNIQUE_IDENTIFIER</a>
 

 

