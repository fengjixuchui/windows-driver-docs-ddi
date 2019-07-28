---
UID: NI:nfcsedev.IOCTL_NFCSE_HCE_REMOTE_SEND
title: IOCTL_NFCSE_HCE_REMOTE_SEND (nfcsedev.h)
description: Transmits response APDU from DeviceHost NFCEE to remote device. The caller must be sure that response APDU is conformant to ISO-IEC 7816-4.
old-location: nfpdrivers\ioctl_nfcse_hce_remote_send.htm
tech.root: nfpdrivers
ms.assetid: 5BA627C9-747D-493A-B568-B2912BBB622F
ms.date: 02/15/2018
ms.keywords: IOCTL_NFCSE_HCE_REMOTE_SEND, IOCTL_NFCSE_HCE_REMOTE_SEND control, IOCTL_NFCSE_HCE_REMOTE_SEND control code [Near-Field Proximity Drivers], nfcsedev/IOCTL_NFCSE_HCE_REMOTE_SEND, nfpdrivers.ioctl_nfcse_hce_remote_send
ms.topic: ioctl
f1_keywords:
 - "nfcsedev/IOCTL_NFCSE_HCE_REMOTE_SEND"
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
- IOCTL_NFCSE_HCE_REMOTE_SEND
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_NFCSE_HCE_REMOTE_SEND IOCTL


## -description


Transmits response APDU from DeviceHost NFCEE to remote device. The caller must be sure that response APDU is conformant to ISO-IEC 7816-4.




## -ioctlparameters




### -input-buffer

Pointer to buffer containing <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/nfcsedev/ns-nfcsedev-_secure_element_hce_data_packet">SECURE_ELEMENT_HCE_DATA_PACKET</a> structure.



### -input-buffer-length

sizeof(SECURE_ELEMENT_HCE_DATA_PACKET)


### -output-buffer

None


### -output-buffer-length

None


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
<td><b>STATUS_INVALID_PARAMETER</b></td>
<td>This code is returned if the input connection ID does not match the current connection ID.</td>
</tr>
<tr>
<td><b>STATUS_INVALID_DEVICE_STATE</b></td>
<td> This code is returned if the IOCTL is sent on a handle other than with relative name ‘SEManage’.</td>
</tr>
</table>
 

