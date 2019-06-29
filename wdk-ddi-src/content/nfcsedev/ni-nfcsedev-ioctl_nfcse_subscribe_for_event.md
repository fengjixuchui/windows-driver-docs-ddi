---
UID: NI:nfcsedev.IOCTL_NFCSE_SUBSCRIBE_FOR_EVENT
title: IOCTL_NFCSE_SUBSCRIBE_FOR_EVENT (nfcsedev.h)
description: The IOCTL_NFCSE_SUBSCRIBE_FOR_EVENT control code is issued by a client to subscribe to a specific event.
old-location: nfpdrivers\ioctl_nfcse_subscribe_for_event.htm
tech.root: nfpdrivers
ms.assetid: 3A184392-A68C-4AFC-AE9F-36247153ADD2
ms.date: 02/15/2018
ms.keywords: IOCTL_NFCSE_SUBSCRIBE_FOR_EVENT, IOCTL_NFCSE_SUBSCRIBE_FOR_EVENT control, IOCTL_NFCSE_SUBSCRIBE_FOR_EVENT control code [Near-Field Proximity Drivers], nfcsedev/IOCTL_NFCSE_SUBSCRIBE_FOR_EVENT, nfpdrivers.ioctl_nfcse_subscribe_for_event
ms.topic: ioctl
req.header: nfcsedev.h
req.include-header: 
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
- nfcsedev.h
api_name:
- IOCTL_NFCSE_SUBSCRIBE_FOR_EVENT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_NFCSE_SUBSCRIBE_FOR_EVENT IOCTL


## -description


The <b>IOCTL_NFCSE_SUBSCRIBE_FOR_EVENT</b> 
   control code is issued by a client to subscribe to a specific event. 


## -ioctlparameters




### -input-buffer


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/nfcsedev/ns-nfcsedev-_secure_element_event_subscription_info"> SECURE_ELEMENT_EVENT_SUBSCRIPTION_INFO</a> structure.



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
<th>Return Code</th>
<th>Description</th>
</tr>
<tr>
<td><b>STATUS_INVALID_DEVICE_STATE</b></td>
<td>This code is returned when this IOCTL is called on a device handle with a filename other than <b>SEEvents</b>, or there is already another pending request that is not completed yet.</td>
</tr>
<tr>
<td><b>STATUS_FEATURE_NOT_SUPPORTED</b></td>
<td>  This code is returned when the output is non-zero, or when the GUID of the secure element does not match any of the enumerated IDs.</td>
</tr>
</table>
 


## -remarks



The following are requirements that the driver must adhere to.<ul>
<li>This IOCTL must be called on a handle with a <b>SEEvents</b> file name; otherwise, the driver returns STATUS_INVALID_DEVICE_STATE.</li>
<li><b>GUID_NULL</b> can be specified by the client as a wild card to subscribe for a specific event from all enumerated secure elements.</li>
</ul>




