---
UID: NF:usbdlib.USBD_QueryBusTime
title: USBD_QueryBusTime function (usbdlib.h)
description: The USBD_QueryBusTime routine has been deprecated in Windows XP and later operating systems. Do not use.
old-location: buses\usbd_querybustime.htm
tech.root: usbref
ms.assetid: ae59daf6-da7b-4b04-bb5c-dfd353b937a0
ms.date: 05/07/2018
keywords: ["USBD_QueryBusTime function"]
ms.keywords: USBD_QueryBusTime, USBD_QueryBusTime routine [Buses], buses.usbd_querybustime, usbdlib/USBD_QueryBusTime, usbfunc_2911ce15-3106-4c66-95c8-52ff57318131.xml
f1_keywords:
 - "usbdlib/USBD_QueryBusTime"
 - "USBD_QueryBusTime"
req.header: usbdlib.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Deprecated.
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
req.lib: Usbd.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Usbd.lib
- Usbd.dll
api_name:
- USBD_QueryBusTime
targetos: Windows
req.typenames: 
---

# USBD_QueryBusTime function


## -description


The <b>USBD_QueryBusTime</b> routine has been deprecated in Windows XP and later operating systems. Do not use. 

See URB_FUNCTION_GET_CURRENT_FRAME_NUMBER for equivalent functionality that is supported on all versions of Windows.


## -parameters




### -param RootHubPdo [in]

Obsolete.




### -param CurrentFrame [out]

Obsolete.




## -returns



This routine does not return a value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_get_current_frame_number">URB_GET_CURRENT_FRAME_NUMBER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_usbref/">USB device driver programming reference</a>
 

 

