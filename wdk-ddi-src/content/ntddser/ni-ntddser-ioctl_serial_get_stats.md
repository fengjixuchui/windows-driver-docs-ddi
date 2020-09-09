---
UID: NI:ntddser.IOCTL_SERIAL_GET_STATS
title: IOCTL_SERIAL_GET_STATS (ntddser.h)
description: The IOCTL_SERIAL_GET_STATS request returns information about the performance of a serial controller.
old-location: serports\ioctl_serial_get_stats.htm
tech.root: serports
ms.assetid: 264b8460-acda-46ba-b070-e2956f7cfc50
ms.date: 04/23/2018
keywords: ["IOCTL_SERIAL_GET_STATS IOCTL"]
ms.keywords: IOCTL_SERIAL_GET_STATS, IOCTL_SERIAL_GET_STATS control, IOCTL_SERIAL_GET_STATS control code [Serial Ports], ntddser/IOCTL_SERIAL_GET_STATS, serports.ioctl_serial_get_stats, serref_c5deddd3-8649-4628-a62e-810d4693052e.xml
req.header: ntddser.h
req.include-header: Ntddser.h
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
 - IOCTL_SERIAL_GET_STATS
 - ntddser/IOCTL_SERIAL_GET_STATS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddser.h
api_name:
 - IOCTL_SERIAL_GET_STATS
---

# IOCTL_SERIAL_GET_STATS IOCTL


## -description

The <b>IOCTL_SERIAL_GET_STATS</b> request returns information about the performance of a serial controller. The statistics include the number of characters transmitted, the number of characters received, and useful error statistics. The driver continuously increments performance values.

To reset the accumulated performance values to zero, a client can use an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_clear_stats">IOCTL_SERIAL_CLEAR_STATS</a> request.

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated <b>SERIALPERF_STATS</b> structure that the serial controller driver uses to output performance information.

### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serialperf_stats">SERIALPERF_STATS</a> structure.

### -in-out-buffer

### -inout-buffer-length

### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_clear_stats">IOCTL_SERIAL_CLEAR_STATS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serialperf_stats">SERIALPERF_STATS</a>

