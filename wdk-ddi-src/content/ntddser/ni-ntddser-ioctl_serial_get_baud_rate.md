---
UID: NI:ntddser.IOCTL_SERIAL_GET_BAUD_RATE
title: IOCTL_SERIAL_GET_BAUD_RATE (ntddser.h)
description: The IOCTL_SERIAL_GET_BAUD_RATE request returns the baud rate at which the serial port is currently configured to transmit and receive data.
old-location: serports\ioctl_serial_get_baud_rate.htm
tech.root: serports
ms.assetid: 074ab68e-7cd5-44e4-b3f6-2d6ddc5f3095
ms.date: 04/23/2018
keywords: ["IOCTL_SERIAL_GET_BAUD_RATE IOCTL"]
ms.keywords: IOCTL_SERIAL_GET_BAUD_RATE, IOCTL_SERIAL_GET_BAUD_RATE control, IOCTL_SERIAL_GET_BAUD_RATE control code [Serial Ports], ntddser/IOCTL_SERIAL_GET_BAUD_RATE, serports.ioctl_serial_get_baud_rate, serref_d3a435b0-2934-465a-9c60-91210895755e.xml
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
 - IOCTL_SERIAL_GET_BAUD_RATE
 - ntddser/IOCTL_SERIAL_GET_BAUD_RATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddser.h
api_name:
 - IOCTL_SERIAL_GET_BAUD_RATE
---

# IOCTL_SERIAL_GET_BAUD_RATE IOCTL


## -description

The <b>IOCTL_SERIAL_GET_BAUD_RATE</b> request returns the baud rate at which the serial port is currently configured to transmit and receive data.

To set the baud rate, a client can use an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_baud_rate">IOCTL_SERIAL_SET_BAUD_RATE</a> request.

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated <b>SERIAL_BAUD_RATE</b> structure that the serial controller driver uses to output the baud rate information.

### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size in bytes of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_baud_rate">SERIAL_BAUD_RATE</a> structure.

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the request is successful, the <b>Information</b> member is set to the size in bytes of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_baud_rate">SERIAL_BAUD_RATE</a> structure. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_baud_rate">IOCTL_SERIAL_SET_BAUD_RATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_baud_rate">SERIAL_BAUD_RATE</a>

