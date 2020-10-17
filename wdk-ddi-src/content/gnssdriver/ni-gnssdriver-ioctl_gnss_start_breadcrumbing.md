---
UID: NI:gnssdriver.IOCTL_GNSS_START_BREADCRUMBING
title: IOCTL_GNSS_START_BREADCRUMBING (gnssdriver.h)
description: The IOCTL_GNSS_START_BREADCRUMBING control code is used to start and configure breadcrumbing.
old-location: gnss\ioctl_gnss_start_breadcrumbing.htm
tech.root: gnss
ms.assetid: 0BC08081-5A7B-48B7-98D5-A6155CAE5CC9
ms.date: 02/15/2018
keywords: ["IOCTL_GNSS_START_BREADCRUMBING IOCTL"]
ms.keywords: IOCTL_GNSS_START_BREADCRUMBING, IOCTL_GNSS_START_BREADCRUMBING control, IOCTL_GNSS_START_BREADCRUMBING control code [Sensor Devices], gnss.ioctl_gnss_start_breadcrumbing, gnssdriver/IOCTL_GNSS_START_BREADCRUMBING
req.header: gnssdriver.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_GNSS_START_BREADCRUMBING
 - gnssdriver/IOCTL_GNSS_START_BREADCRUMBING
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - IOCTL_GNSS_START_BREADCRUMBING
---

# IOCTL_GNSS_START_BREADCRUMBING IOCTL


## -description

The <b>IOCTL_GNSS_START_BREADCRUMBING</b> control code is used to start and configure breadcrumbing.

## -ioctlparameters

### -input-buffer

Pointer to the input buffer.

### -input-buffer-length

Size of the input buffer.

### -output-buffer

Pointer to the output buffer.

### -output-buffer-length

Size of the output buffer.

### -in-out-buffer

### -inout-buffer-length

### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="/windows-hardware/drivers/kernel/using-ntstatus-values">NTSTATUS</a> code.

## -see-also

<a href="/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>