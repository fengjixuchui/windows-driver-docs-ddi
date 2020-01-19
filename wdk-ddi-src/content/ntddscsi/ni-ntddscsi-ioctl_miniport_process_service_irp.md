---
UID: NI:ntddscsi.IOCTL_MINIPORT_PROCESS_SERVICE_IRP
title: IOCTL_MINIPORT_PROCESS_SERVICE_IRP (ntddscsi.h)
description: This IOCTL is used by a user-mode application or kernel-mode driver that requires notification when something of interest happens in the virtual miniport.
old-location: storage\ioctl_miniport_process_service_irp.htm
tech.root: storage
ms.assetid: 5d9f695c-9a9f-4af9-8bf6-2096f3278852
ms.date: 03/29/2018
ms.keywords: IOCTL_MINIPORT_PROCESS_SERVICE_IRP, IOCTL_MINIPORT_PROCESS_SERVICE_IRP control, IOCTL_MINIPORT_PROCESS_SERVICE_IRP control code [Storage Devices], k307_8997b602-e4ce-4b15-be19-77ba863de295.xml, ntddscsi/IOCTL_MINIPORT_PROCESS_SERVICE_IRP, storage.ioctl_miniport_process_service_irp
ms.topic: ioctl
f1_keywords:
 - "ntddscsi/IOCTL_MINIPORT_PROCESS_SERVICE_IRP"
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
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
- Ntddscsi.h
api_name:
- IOCTL_MINIPORT_PROCESS_SERVICE_IRP
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_MINIPORT_PROCESS_SERVICE_IRP IOCTL


## -description



This IOCTL is used by a user-mode application or kernel-mode driver that requires notification when something of interest happens in the virtual miniport. This IOCTL might be used, for example, when a vendor-specific, time-consuming operation such as device discovery completes.




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains a user-defined structure. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> indicates the size, in bytes, of all the input data.


### -output-buffer

Updated user-defined structures are returned in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

The length of the buffer.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field contains the number of bytes returned in the output buffer. The <b>Status</b> field indicates the results of the operation.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_process_service_request">HwStorProcessServiceRequest</a>
 

 

