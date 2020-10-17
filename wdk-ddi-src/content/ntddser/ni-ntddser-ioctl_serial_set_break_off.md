---
UID: NI:ntddser.IOCTL_SERIAL_SET_BREAK_OFF
title: IOCTL_SERIAL_SET_BREAK_OFF (ntddser.h)
description: The IOCTL_SERIAL_SET_BREAK_OFF request sets the line control break signal inactive.
old-location: serports\ioctl_serial_set_break_off.htm
tech.root: serports
ms.assetid: aa64da58-cb50-485e-afbc-3a0408b4ecf2
ms.date: 04/23/2018
keywords: ["IOCTL_SERIAL_SET_BREAK_OFF IOCTL"]
ms.keywords: IOCTL_SERIAL_SET_BREAK_OFF, IOCTL_SERIAL_SET_BREAK_OFF control, IOCTL_SERIAL_SET_BREAK_OFF control code [Serial Ports], ntddser/IOCTL_SERIAL_SET_BREAK_OFF, serports.ioctl_serial_set_break_off, serref_1a347f28-6dfb-4b5d-afb8-9bb8ffad9f36.xml
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
 - IOCTL_SERIAL_SET_BREAK_OFF
 - ntddser/IOCTL_SERIAL_SET_BREAK_OFF
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddser.h
api_name:
 - IOCTL_SERIAL_SET_BREAK_OFF
---

# IOCTL_SERIAL_SET_BREAK_OFF IOCTL


## -description

The <b>IOCTL_SERIAL_SET_BREAK_OFF</b> request sets the line control break signal inactive.

To set the line control break signal active, a client can use an <a href="/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_break_on">IOCTL_SERIAL_SET_BREAK_ON</a> request.

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> member is set to zero.

The <b>Status</b> member is to one of the <a href="/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_break_on">IOCTL_SERIAL_SET_BREAK_ON</a>