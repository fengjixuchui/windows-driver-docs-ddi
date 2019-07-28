---
UID: NS:ntddstor._STORAGE_DEVICE_ID_DESCRIPTOR
title: _STORAGE_DEVICE_ID_DESCRIPTOR (ntddstor.h)
description: The STORAGE_DEVICE_ID_DESCRIPTOR structure is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the device ID descriptor data for a device.
old-location: storage\storage_device_id_descriptor.htm
tech.root: storage
ms.assetid: e0e1bd3e-ee8d-40f2-904d-d6dcc4185406
ms.date: 03/29/2018
ms.keywords: PSTORAGE_DEVICE_ID_DESCRIPTOR, PSTORAGE_DEVICE_ID_DESCRIPTOR structure pointer [Storage Devices], STORAGE_DEVICE_ID_DESCRIPTOR, STORAGE_DEVICE_ID_DESCRIPTOR structure [Storage Devices], _STORAGE_DEVICE_ID_DESCRIPTOR, ntddstor/PSTORAGE_DEVICE_ID_DESCRIPTOR, ntddstor/STORAGE_DEVICE_ID_DESCRIPTOR, storage.storage_device_id_descriptor, structs-general_65dcf7da-1241-4d3d-b8c6-a53c15c0763c.xml
ms.topic: struct
f1_keywords:
 - "ntddstor/STORAGE_DEVICE_ID_DESCRIPTOR"
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
- ntddstor.h
api_name:
- STORAGE_DEVICE_ID_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: STORAGE_DEVICE_ID_DESCRIPTOR, PSTORAGE_DEVICE_ID_DESCRIPTOR
---

# _STORAGE_DEVICE_ID_DESCRIPTOR structure


## -description


The <b>STORAGE_DEVICE_ID_DESCRIPTOR</b> structure is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a> request to retrieve the device ID descriptor data for a device.  


## -struct-fields




### -field Version

Indicates the version of the descriptor.


### -field Size

Indicates the size in bytes of the descriptor.


### -field NumberOfIdentifiers

Contains the number of identifiers reported by the device in the <b>Identifiers</b> array.


### -field Identifiers

Contains a variable-length array of identification descriptors.


## -remarks



The device descriptor consists of an array of device IDs taken from the SCSI-3 vital product page data that was retrieved during discovery.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_storage_adapter_descriptor">STORAGE_ADAPTER_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_storage_descriptor_header">STORAGE_DESCRIPTOR_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_storage_device_descriptor">STORAGE_DEVICE_DESCRIPTOR</a>
 

 

