---
UID: NI:avc.IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO
title: IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO (avc.h)
description: The IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO I/O control code controls the enumeration of virtual subunits.
old-location: stream\ioctl_avc_remove_virtual_subunit_info.htm
tech.root: stream
ms.assetid: 0058b595-e807-4908-89b1-3956effba4db
ms.date: 04/23/2018
keywords: ["IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO IOCTL"]
ms.keywords: IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO, IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO control, IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO control code [Streaming Media Devices], avc/IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO, avcref_b337d332-db69-4a9d-8e5e-d261ebf0cdd8.xml, stream.ioctl_avc_remove_virtual_subunit_info
f1_keywords:
 - "avc/IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO"
req.header: avc.h
req.include-header: Avc.h
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
- avc.h
api_name:
- IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO IOCTL


## -description



The IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO I/O control code controls the enumeration of virtual subunits. It is available to user mode as well as kernel-mode components through the IRP_MJ_DEVICE_CONTROL dispatch. For driver-to-driver communication, it is a METHOD_BUFFERED IOCTL, so set the IRP fields accordingly (IrpStack->Parameters.DeviceIoControl.InputBufferLength and Irp->AssociatedIrp.SystemBuffer).

IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO is used to remove all subunit IDs of a single type. The ID part of the subunit address is ignored.

This IOCTL uses the AVC_SUBUNIT_ADDR_SPEC structure.




## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

If successful, the AV/C protocol driver sets <b>Irp->IoStatus.Status </b>to STATUS_SUCCESS.

Possible other return values include:

<table>
<tr>
<th>Return Value</th>
<th>Description</th>
</tr>
<tr>
<td>
STATUS_INSUFFICIENT_RESOURCES

</td>
<td>
No buffer was passed, or insufficient resources available to perform a registry query.

</td>
</tr>
<tr>
<td>
STATUS_INVALID_BUFFER_SIZE

</td>
<td>
The buffer passed in Irp->AssociatedIrp.SystemBuffer must be at least as large as sizeof(AVC_SUBUNIT_ADDR_SPEC) which includes a single-byte subunit address, but limited to a 32 byte subunit address.

</td>
</tr>
<tr>
<td>
STATUS_INVALID_PARAMETER

</td>
<td>
The subunit address was specified incorrectly.

</td>
</tr>
<tr>
<td>
STATUS_ACCESS_DENIED

</td>
<td>
The current user has insufficient registry access privileges to make the update persistent.

</td>
</tr>
</table>
 


## -remarks



Must be called at IRQL = PASSIVE_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ns-avc-_avc_subunit_addr_spec">AVC_SUBUNIT_ADDR_SPEC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ni-avc-ioctl_avc_bus_reset">IOCTL_AVC_BUS_RESET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ni-avc-ioctl_avc_class">IOCTL_AVC_CLASS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ni-avc-ioctl_avc_update_virtual_subunit_info">IOCTL_AVC_UPDATE_VIRTUAL_SUBUNIT_INFO</a>
 

 


