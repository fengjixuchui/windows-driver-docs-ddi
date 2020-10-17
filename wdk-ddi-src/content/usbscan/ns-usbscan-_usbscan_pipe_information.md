---
UID: NS:usbscan._USBSCAN_PIPE_INFORMATION
title: _USBSCAN_PIPE_INFORMATION (usbscan.h)
description: The USBSCAN_PIPE_INFORMATION structure is used to describe a USB transfer pipe for a still image device. An array of USBSCAN_PIPE_INFORMATION structures is supplied within a USBSCAN_PIPE_CONFIGURATION structure.
old-location: image\usbscan_pipe_information.htm
tech.root: image
ms.assetid: a13bec15-67e1-45f9-be90-dee5c555ad64
ms.date: 05/03/2018
keywords: ["USBSCAN_PIPE_INFORMATION structure"]
ms.keywords: "*PUSBSCAN_PIPE_INFORMATION, PUSBSCAN_PIPE_INFORMATION, PUSBSCAN_PIPE_INFORMATION structure pointer [Imaging Devices], USBSCAN_PIPE_INFORMATION, USBSCAN_PIPE_INFORMATION structure [Imaging Devices], _USBSCAN_PIPE_INFORMATION, image.usbscan_pipe_information, stifnc_3a31b5a2-4bd9-4e95-b10d-959c6caa8754.xml, usbscan/PUSBSCAN_PIPE_INFORMATION, usbscan/USBSCAN_PIPE_INFORMATION"
req.header: usbscan.h
req.include-header: Usbscan.h
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
req.typenames: USBSCAN_PIPE_INFORMATION, *PUSBSCAN_PIPE_INFORMATION
f1_keywords:
 - _USBSCAN_PIPE_INFORMATION
 - usbscan/_USBSCAN_PIPE_INFORMATION
 - PUSBSCAN_PIPE_INFORMATION
 - usbscan/PUSBSCAN_PIPE_INFORMATION
 - USBSCAN_PIPE_INFORMATION
 - usbscan/USBSCAN_PIPE_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbscan.h
api_name:
 - USBSCAN_PIPE_INFORMATION
---

# _USBSCAN_PIPE_INFORMATION structure


## -description

The USBSCAN_PIPE_INFORMATION structure is used to describe a USB transfer pipe for a still image device. An array of USBSCAN_PIPE_INFORMATION structures is supplied within a <a href="/windows-hardware/drivers/ddi/usbscan/ns-usbscan-_usbscan_pipe_configuration">USBSCAN_PIPE_CONFIGURATION</a> structure.

## -struct-fields

### -field MaximumPacketSize

Maximum packet size for the transfer pipe.

### -field EndpointAddress

The address of the pipe's endpoint. The address is encoded as follows:

<table>
<tr>
<th>Bits</th>
<th>Definition</th>
</tr>
<tr>
<td>
0..3

</td>
<td>
Endpoint number.

</td>
</tr>
<tr>
<td>
4..6

</td>
<td>
Reserved, set to 0.

</td>
</tr>
<tr>
<td>
7

</td>
<td>
Direction, ignored for control endpoints:

0 - OUT endpoint

1 - IN endpoint

</td>
</tr>
</table>
 

For more information, see the <i>Universal Serial Bus Specification</i>.

### -field Interval

Polling interval, in milliseconds, for interrupt pipes. For more information, see the <i>Universal Serial Bus Specification</i>.

### -field PipeType

A <a href="/windows-hardware/drivers/ddi/usbscan/ne-usbscan-_raw_pipe_type">RAW_PIPE_TYPE</a>-typed value identifying the pipe type.

## -see-also

<a href="/windows-hardware/drivers/ddi/usbscan/ne-usbscan-_raw_pipe_type">RAW_PIPE_TYPE</a>



<a href="/windows-hardware/drivers/ddi/usbscan/ns-usbscan-_usbscan_pipe_configuration">USBSCAN_PIPE_CONFIGURATION</a>