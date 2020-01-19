---
UID: NI:d4drvif.IOCTL_DOT4_LAST
title: IOCTL_DOT4_LAST (d4drvif.h)
description: This topic describes IOCTL_DOT4_LAST.
old-location: print\ioctl_ioctl_dot4_last.htm
tech.root: print
ms.assetid: 4891CF79-F08F-4043-A596-1E3E0BCF879D
ms.date: 04/20/2018
ms.keywords: IOCTL_DOT4_LAST, IOCTL_DOT4_LAST control, IOCTL_DOT4_LAST control code [Print Devices], d4drvif/IOCTL_DOT4_LAST, print.ioctl_ioctl_dot4_last
ms.topic: ioctl
f1_keywords:
 - "d4drvif/IOCTL_DOT4_LAST"
req.header: d4drvif.h
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
- D4drvif.h
api_name:
- IOCTL_DOT4_LAST
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_DOT4_LAST IOCTL


## -description


This topic describes <b>IOCTL_DOT4_LAST</b>.


## -ioctlparameters




### -input-buffer




### -input-buffer-length




### -output-buffer




### -output-buffer-length




### -in-out-buffer




### -inout-buffer-length




### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

