---
UID: NS:ucxusbdevice._USBDEVICE_MGMT_HEADER
title: _USBDEVICE_MGMT_HEADER (ucxusbdevice.h)
description: This structure provides a handle for the Universal Serial Bus (USB) hub or device physically connected to the bus.
old-location: buses\_usbdevice_mgmt_header.htm
tech.root: usbref
ms.assetid: E3CDED41-FE83-4CBC-9FF8-4858125F7108
ms.date: 05/07/2018
keywords: ["_USBDEVICE_MGMT_HEADER structure"]
ms.keywords: "*PUSBDEVICE_MGMT_HEADER, P_USBDEVICE_MGMT_HEADER, P_USBDEVICE_MGMT_HEADER structure pointer [Buses], USBDEVICE_MGMT_HEADER, USBDEVICE_MGMT_HEADER structure [Buses], _USBDEVICE_MGMT_HEADER, buses._usbdevice_mgmt_header, ucxusbdevice/P_USBDEVICE_MGMT_HEADER, ucxusbdevice/_USBDEVICE_MGMT_HEADER"
f1_keywords:
 - "ucxusbdevice/USBDEVICE_MGMT_HEADER"
 - "USBDEVICE_MGMT_HEADER"
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
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
- ucxusbdevice.h
api_name:
- USBDEVICE_MGMT_HEADER
targetos: Windows
req.typenames: USBDEVICE_MGMT_HEADER, *PUSBDEVICE_MGMT_HEADER
---

# _USBDEVICE_MGMT_HEADER structure


## -description


This structure provides a handle  for the Universal Serial Bus (USB) hub or device physically connected to the bus.


## -struct-fields




### -field Size

The size in bytes of this structure.


### -field Hub

The handle to the USB hub that is physically connected to the bus.


### -field UsbDevice

The handle for the USB device that is physically connected to the bus.

