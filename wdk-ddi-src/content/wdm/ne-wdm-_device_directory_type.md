---
UID: NE:wdm._DEVICE_DIRECTORY_TYPE
title: _DEVICE_DIRECTORY_TYPE (wdm.h)
description: The directory from which the driver is loaded. 
ms.assetid: d49e913a-dadb-4669-b3a4-e08a60b2a767
ms.date: 10/19/2018
ms.topic: enum
f1_keywords:
 - "wdm/_DEVICE_DIRECTORY_TYPE"
ms.keywords: _DEVICE_DIRECTORY_TYPE, DEVICE_DIRECTORY_TYPE, *PDEVICE_DIRECTORY_TYPE, 
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: DEVICE_DIRECTORY_TYPE, *PDEVICE_DIRECTORY_TYPE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- wdm.h
api_name: 
- _DEVICE_DIRECTORY_TYPE
product:
- Windows
targetos: Windows
---

# _DEVICE_DIRECTORY_TYPE enumeration

## -description

Defines values for the type of directory used by the driver to load and store files specific to a device instance. This enumeration is used by the [**IoGetDeviceDirectory**](nf-wdm-iogetdevicedirectory.md) function.


## -enum-fields

### -field DeviceDirectoryData

The requested directory is a general-purpose directory in which the driver stores files, specific to a device instance. 

## -remarks

## -see-also
[**IoGetDeviceDirectory**](nf-wdm-iogetdevicedirectory.md) 
