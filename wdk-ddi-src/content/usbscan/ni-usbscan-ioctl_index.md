---
UID: NI:usbscan.IOCTL_INDEX
title: IOCTL_INDEX (usbscan.h)
description: 
ms.assetid: 5f05ce18-4a4a-433c-8cab-402f0ea39155
ms.date: 10/19/2018
keywords: ["IOCTL_INDEX IOCTL"]
req.header: usbscan.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.max-support: 
targetos: Windows
ms.custom: RS5
f1_keywords:
 - IOCTL_INDEX
 - usbscan/IOCTL_INDEX
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - usbscan.h
api_name:
 - IOCTL_INDEX
product:
 - Windows
---

# IOCTL_INDEX IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)


## -description

## -ioctlparameters

### -input-buffer

### -input-buffer-length 

### -output-buffer

### -output-buffer-length 

### -in-out-buffer

### -inout-buffer-length 

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code. 
For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

## -see-also