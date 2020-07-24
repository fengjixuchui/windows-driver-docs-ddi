---
UID: NI:winsmcrd.IOCTL_SMARTCARD_SWALLOW
title: IOCTL_SMARTCARD_SWALLOW (winsmcrd.h)
description: The IOCTL_SMARTCARD_SWALLOW request causes the smart card reader to swallow the card.
old-location: smartcrd\ioctl_smartcard_swallow.htm
tech.root: smartcrd
ms.assetid: c229769d-8798-436e-bd26-9dfd507fba9c
ms.date: 02/22/2018
keywords: ["IOCTL_SMARTCARD_SWALLOW IOCTL"]
ms.keywords: IOCTL_SMARTCARD_SWALLOW, IOCTL_SMARTCARD_SWALLOW control, IOCTL_SMARTCARD_SWALLOW control code [Smart Card Reader Devices], scioctls_71a14048-5e68-45c7-ad72-03c6350b9072.xml, smartcrd.ioctl_smartcard_swallow, winsmcrd/IOCTL_SMARTCARD_SWALLOW
f1_keywords:
 - "winsmcrd/IOCTL_SMARTCARD_SWALLOW"
 - "IOCTL_SMARTCARD_SWALLOW"
req.header: winsmcrd.h
req.include-header: Winsmcrd.h
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
- Winsmcrd.h
api_name:
- IOCTL_SMARTCARD_SWALLOW
targetos: Windows
req.typenames: 
---

# IOCTL_SMARTCARD_SWALLOW IOCTL


## -description



The IOCTL_SMARTCARD_SWALLOW request causes the smart card reader to swallow the card.




## -ioctlparameters




### -input-buffer

None 


### -input-buffer-length








### -output-buffer

None 


### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Possible error codes are:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
STATUS_SUCCESS

</td>
<td>
The smart card was swallowed.

</td>
</tr>
<tr>
<td>
STATUS_NO_MEDIA

</td>
<td>
No smart card is in the reader.

</td>
</tr>
<tr>
<td>
STATUS_IO_TIMEOUT

</td>
<td>
The operation timed out.

</td>
</tr>
<tr>
<td>
STATUS_NOT_SUPPORTED

</td>
<td>
The reader does not support swallowing.

</td>
</tr>
</table>
 


## -remarks



The <b>Information</b> member must be set to zero.

The <b>Status</b> member is set to one of the values in the status block table.



