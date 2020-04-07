---
UID: NI:usbscan.IOCTL_ABORT_PIPE
title: IOCTL_ABORT_PIPE (usbscan.h)
description: 
ms.assetid: b532777a-0834-4d70-9cde-060f697e912d
ms.date: 10/19/2018
keywords: ["IOCTL_ABORT_PIPE IOCTL"]
f1_keywords:
 - "usbscan/IOCTL_ABORT_PIPE"
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- usbscan.h
api_name: 
- IOCTL_ABORT_PIPE
product: 
- Windows
targetos: Windows
ms.custom: RS5
---

# IOCTL_ABORT_PIPE IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

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
For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

## -see-also
