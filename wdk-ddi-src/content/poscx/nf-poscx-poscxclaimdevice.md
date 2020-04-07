---
UID: NF:poscx.PosCxClaimDevice
title: PosCxClaimDevice function (poscx.h)
description: PosCxClaimDevice is called to claim a device for exclusive use. The caller should call PosCxReleaseDevice when the device is no longer needed.
old-location: pos\poscxclaimdevice.htm
tech.root: pos
ms.assetid: 16EB583C-FB61-4811-A691-3FBD159F8FD0
ms.date: 02/23/2018
keywords: ["PosCxClaimDevice function"]
ms.keywords: PosCxClaimDevice, PosCxClaimDevice function, pos.poscxclaimdevice, poscx/PosCxClaimDevice
f1_keywords:
 - "poscx/PosCxClaimDevice"
req.header: poscx.h
req.include-header: Poscx.h
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
- poscx.h
api_name:
- PosCxClaimDevice
product:
- Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# PosCxClaimDevice function


## -description


PosCxClaimDevice is called to claim a device for exclusive use. 

The caller should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/poscx/nf-poscx-poscxreleasedevice">PosCxReleaseDevice</a> when the device is no longer needed. 

      

If the device is already claimed, the caller must wait until access is granted.


## -parameters




### -param device [in]

A handle to a framework device object that represents the device.


### -param request [in]

A handle to a framework request object that represents the request. This request must come from a WDF IO queue.


## -returns



Possible return values are:

<table>
<tr>
<td><b>STATUS_SUCCESS</b></td>
<td>The device was successfully claimed.</td>
</tr>
<tr>
<td><b>STATUS_PENDING</b></td>
<td>The claim request was queued.</td>
</tr>
<tr>
<td><b>STATUS_DEVICE_NOT_READY</b></td>
<td>The PosCx library was not successfully initialized.</td>
</tr>
<tr>
<td><b>STATUS_ACCESS_DENIED</b></td>
<td>The current owner has retained device ownership.</td>
</tr>
</table>
 



