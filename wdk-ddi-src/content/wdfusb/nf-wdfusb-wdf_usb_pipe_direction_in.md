---
UID: NF:wdfusb.WDF_USB_PIPE_DIRECTION_IN
title: WDF_USB_PIPE_DIRECTION_IN function (wdfusb.h)
description: The WDF_USB_PIPE_DIRECTION_IN function determines whether a specified USB endpoint is an input endpoint.
old-location: wdf\wdf_usb_pipe_direction_in.htm
tech.root: wdf
ms.assetid: 3fca6d50-ac38-4edf-b24a-ea4fe5d8a4fd
ms.date: 02/26/2018
ms.keywords: DFUsbRef_e0e1b604-8973-4901-91ea-76fce4e69b7c.xml, WDF_USB_PIPE_DIRECTION_IN, WDF_USB_PIPE_DIRECTION_IN function, kmdf.wdf_usb_pipe_direction_in, wdf.wdf_usb_pipe_direction_in, wdfusb/WDF_USB_PIPE_DIRECTION_IN
ms.topic: function
f1_keywords:
 - "wdfusb/WDF_USB_PIPE_DIRECTION_IN"
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: None
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- None
- None.dll
api_name:
- WDF_USB_PIPE_DIRECTION_IN
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_USB_PIPE_DIRECTION_IN function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_USB_PIPE_DIRECTION_IN</b> function determines whether a specified USB endpoint is an input endpoint.


## -parameters




### -param EndpointAddress [in]

A USB endpoint address.


## -returns



<b>WDF_USB_PIPE_DIRECTION_IN</b> returns <b>TRUE</b> if the specified endpoint is an input endpoint. Otherwise, this function returns <b>FALSE</b>.




## -remarks



The high bit of the endpoint address determines the direction (input or output) of an endpoint. For more information about endpoint addresses, see the USB specification.

For more information about the <b>WDF_USB_PIPE_DIRECTION_IN</b> function and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_pipe_direction_out">WDF_USB_PIPE_DIRECTION_OUT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetpipeisinendpoint">WdfUsbTargetPipeIsInEndpoint</a>
 

 

