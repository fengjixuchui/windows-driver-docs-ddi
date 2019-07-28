---
UID: NS:usbioctl._USB_ID_STRING
title: _USB_ID_STRING (usbioctl.h)
description: The USB_ID_STRING structure is used to store a string or multi-string.
old-location: buses\usb_id_string.htm
tech.root: usbref
ms.assetid: e7af07ed-f1a7-4f66-8824-2e12492d037a
ms.date: 05/07/2018
ms.keywords: "*PUSB_ID_STRING, PUSB_ID_STRING, PUSB_ID_STRING structure pointer [Buses], USB_ID_STRING, USB_ID_STRING structure [Buses], _USB_ID_STRING, buses.usb_id_string, usbioctl/PUSB_ID_STRING, usbioctl/USB_ID_STRING"
ms.topic: struct
f1_keywords:
 - "usbioctl/USB_ID_STRING"
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later operating systems.
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
- usbioctl.h
api_name:
- USB_ID_STRING
product:
- Windows
targetos: Windows
req.typenames: USB_ID_STRING, *PUSB_ID_STRING
---

# _USB_ID_STRING structure


## -description


The <b>USB_ID_STRING</b> structure is used to store a string or multi-string.


## -struct-fields




### -field LanguageId

Indicates that language ID of the string.


### -field Pad

 


### -field LengthInBytes

Indicates the length (in bytes) of the string pointed to by <b>Buffer</b>, including the terminating <b>NULL</b>. 


### -field Buffer

Pointer to a string or multi-string.


## -remarks



The reserved members of this structure must be treated as opaque and are reserved for system use.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">USB Structures</a>
 

 

