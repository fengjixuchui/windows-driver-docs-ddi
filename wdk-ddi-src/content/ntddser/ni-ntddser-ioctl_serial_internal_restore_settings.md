---
UID: NI:ntddser.IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS
title: IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS (ntddser.h)
description: The IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS request restores the specified operating mode of a serial device.
old-location: serports\ioctl_serial_internal_restore_settings.htm
tech.root: serports
ms.assetid: 55c56436-ac59-4095-a9f3-f36092db19c0
ms.date: 04/23/2018
keywords: ["IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS IOCTL"]
ms.keywords: IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS, IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS control, IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS control code [Serial Ports], ntddser/IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS, serports.ioctl_serial_internal_restore_settings, serref_bb81345f-080d-4de6-bc36-34a32f934fc7.xml
f1_keywords:
 - "ntddser/IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS"
 - "IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddser.h
api_name:
- IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS IOCTL


## -description



The IOCTL_SERIAL_INTERNAL_RESTORE_SETTINGS request restores the specified operating mode of a serial device. The specified operating mode should be a mode that was returned by an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_internal_basic_settings">IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS</a> request. The operating mode settings should be treated as opaque. Serial does not verify the settings when the settings are restored. Note also that a replacement for Serial might implement a different set of parameters.




## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member of the IRP structure points to a client-allocated SERIAL_BASIC_SETTINGS structure that is used to input operating mode settings. The client should use settings that were returned by an IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS request.


### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member of the IO_STACK_LOCATION structure is set to the size, in bytes, of a SERIAL_BASIC_SETTINGS structure.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request is successful, the <b>Information</b> member is set to the size, in bytes, of SERIAL_BASIC_SETTINGS structure. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>. If Status is set to STATUS_BUFFER_TOO_SMALL, the <b>Parameters.DeviceIoControl.InputBufferLength</b> member of the IO_STACK_LOCATION structure is less than the size, in bytes, of a SERIAL_BASIC_SETTINGS structure.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_internal_basic_settings">IOCTL_SERIAL_INTERNAL_BASIC_SETTINGS</a>
 

 

