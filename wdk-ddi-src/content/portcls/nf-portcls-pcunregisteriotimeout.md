---
UID: NF:portcls.PcUnregisterIoTimeout
title: PcUnregisterIoTimeout function (portcls.h)
description: The PcUnregisterIoTimeout function unregisters a driver-supplied I/O-timer callback routine for a specified device object.
old-location: audio\pcunregisteriotimeout.htm
tech.root: audio
ms.assetid: 4266c775-a2e9-46f0-91ad-6f6cce06bea0
ms.date: 05/08/2018
ms.keywords: PcUnregisterIoTimeout, PcUnregisterIoTimeout function [Audio Devices], audio.pcunregisteriotimeout, audpc-routines_cb67c1bb-c5ad-4118-bdff-906735214653.xml, portcls/PcUnregisterIoTimeout
ms.topic: function
f1_keywords:
 - "portcls/PcUnregisterIoTimeout"
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcUnregisterIoTimeout function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Portcls.lib
- Portcls.dll
api_name:
- PcUnregisterIoTimeout
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcUnregisterIoTimeout function


## -description


The <b>PcUnregisterIoTimeout</b> function unregisters a driver-supplied I/O-timer callback routine for a specified device object.
<div class="alert"><b>Note</b>  This function is deprecated for Windows 8 and later versions of Windows.  For Windows on Arm systems, this function is commented out in the PortCls class driver and is inaccessible.</div><div> </div>

## -parameters




### -param pDeviceObject [in]

Pointer to the same device object that the driver supplied when it previously called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pcregisteriotimeout">PcRegisterIoTimeout</a>. The device object is a system structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>.


### -param pTimerRoutine [in]

Pointer to the same I/O-timer callback routine that the driver supplied when it previously called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pcregisteriotimeout">PcRegisterIoTimeout</a>



### -param pContext [in]

Pointer to the same driver-determined context that the driver supplied when it previously called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pcregisteriotimeout">PcRegisterIoTimeout</a>



## -returns



<b>PcUnregisterIoTimeout</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code. The following table shows some of the possible error codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
Indicates that no timer callback with the same device object, callback routine, and context is currently registered.

</td>
</tr>
</table>
 




## -remarks



This call succeeds only if a time-out callback with the same device object, timer routine, and context was previously registered with a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pcregisteriotimeout">PcRegisterIoTimeout</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pcregisteriotimeout">PcRegisterIoTimeout</a>
 

 

