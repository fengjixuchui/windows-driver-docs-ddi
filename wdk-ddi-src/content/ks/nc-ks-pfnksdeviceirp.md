---
UID: NC:ks.PFNKSDEVICEIRP
title: PFNKSDEVICEIRP (ks.h)
description: An AVStream minidriver's IRP handler routine is called when these IRPs is dispatched by the device.IRP_MN_QUERY_REMOVE_DEVICEIRP_MN_QUERY_STOP_DEVICEIRP_MN_QUERY_INTERFACE
old-location: stream\avstrminidevicequeryremove.htm
tech.root: stream
ms.assetid: c31d7e52-46f7-46b9-9fa2-1778f2301b4d
ms.date: 04/23/2018
keywords: ["PFNKSDEVICEIRP callback function"]
ms.keywords: AVStrMiniDeviceQueryInterface, AVStrMiniDeviceQueryRemove, AVStrMiniDeviceQueryRemove routine [Streaming Media Devices], PFNKSDEVICEIRP, avstclbk_e4e3e23a-c4e7-47fb-ad10-6a0a630669ed.xml, ks/AVStrMiniDeviceQueryRemove, stream.avstrminidevicequeryremove
f1_keywords:
 - "ks/AVStrMiniDeviceQueryRemove"
 - "AVStrMiniDeviceQueryRemove"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.irql: PASSIVE_LEVEL (See Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ks.h
api_name:
- AVStrMiniDeviceQueryRemove
targetos: Windows
req.typenames: 
---

# PFNKSDEVICEIRP callback function


## -description


An AVStream minidriver's IRP handler routine is called when these IRPs is dispatched by the device.


<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-remove-device">IRP_MN_QUERY_REMOVE_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-stop-device">IRP_MN_QUERY_STOP_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-interface">IRP_MN_QUERY_INTERFACE</a>



## -parameters




### -param Device [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a> that dispatched the IRP.


### -param Irp [in]

The IRP issued by <i>Device</i>.


## -returns



Should return STATUS_SUCCESS or the error code that was returned from the attempt to perform the operation. If this is not the case, return an appropriate error code.




## -remarks



<table>
<tr>
<th>IRP</th>
<th>Description</th>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-remove-device">IRP_MN_QUERY_REMOVE_DEVICE</a>
</td>
<td>
The minidriver specifies this routine's address in the <b>QueryRemove</b> member of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice_dispatch">KSDEVICE_DISPATCH</a> structure.

This routine is called when an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-remove-device">IRP_MN_QUERY_REMOVE_DEVICE</a> is dispatched by the device. It will usually be provided by minidrivers that want to prevent removal of the device or by minidrivers that must disallow activity that would otherwise prevent them from committing to a device removal operation. If this routine is not provided, AVStream will assume that the device can commit to a removal.

The routine is called at IRQL = PASSIVE_LEVEL and may not return STATUS_PENDING; a success code indicates that the device can commit to a removal and an error code indicates that it cannot.

Return success if the device can be removed (or drivers can be updated) without disrupting the machine.

This routine is optional.

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-stop-device">IRP_MN_QUERY_STOP_DEVICE</a>
</td>
<td>
The minidriver specifies a pointer to this routine in the <b>QueryStop</b> member of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice_dispatch">KSDEVICE_DISPATCH</a> structure.

Use <i>AVStrMiniQueryStop</i> to prevent the stopping of the device or to disallow activity that would prevent the minidriver from committing to a stop operation. If this routine is not specified, AVStream assumes that the minidriver can commit to a stop operation.

This routine is optional.

Success indicates that the device can commit to a stop and an error code indicates that it cannot. Do not return STATUS_PENDING.

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-interface">IRP_MN_QUERY_INTERFACE</a>
</td>
<td>
A driver or system component sends this IRP to get information about an interface exported by your driver. For more information about the IRP, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-interface">IRP_MN_QUERY_INTERFACE</a>.

The minidriver specifies this routine's address in the <b>QueryInterface</b> member of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice_dispatch">KSDEVICE_DISPATCH</a> structure.

This routine is optional.

</td>
</tr>
</table>
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice_dispatch">KSDEVICE_DISPATCH</a>
 

 

