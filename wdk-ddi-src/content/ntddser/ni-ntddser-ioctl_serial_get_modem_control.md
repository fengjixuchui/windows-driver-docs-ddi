---
UID: NI:ntddser.IOCTL_SERIAL_GET_MODEM_CONTROL
title: IOCTL_SERIAL_GET_MODEM_CONTROL (ntddser.h)
description: The IOCTL_SERIAL_GET_MODEM_CONTROL request returns the value of the modem control register in the serial controller.
old-location: serports\ioctl_serial_get_modem_control.htm
tech.root: serports
ms.assetid: 4b3f52ee-8028-4cba-a8c7-4ba73b1fcab0
ms.date: 04/23/2018
ms.keywords: IOCTL_SERIAL_GET_MODEM_CONTROL, IOCTL_SERIAL_GET_MODEM_CONTROL control, IOCTL_SERIAL_GET_MODEM_CONTROL control code [Serial Ports], ntddser/IOCTL_SERIAL_GET_MODEM_CONTROL, serports.ioctl_serial_get_modem_control, serref_063be160-c01f-40c9-aff9-2de802c70bda.xml
ms.topic: ioctl
f1_keywords:
 - "ntddser/IOCTL_SERIAL_GET_MODEM_CONTROL"
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
- Ntddser.h
api_name:
- IOCTL_SERIAL_GET_MODEM_CONTROL
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_GET_MODEM_CONTROL IOCTL


## -description


The <b>IOCTL_SERIAL_GET_MODEM_CONTROL</b> request returns the value of the modem control register in the serial controller.

To set the modem control register, a client can use an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddser/ni-ntddser-ioctl_serial_set_modem_control">IOCTL_SERIAL_SET_MODEM_CONTROL</a> request.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated ULONG buffer that the serial controller driver uses to output the value of the modem control register.


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a ULONG.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a ULONG. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## -remarks



The <b>IOCTL_SERIAL_GET_MODEM_CONTROL</b> and <b>IOCTL_SERIAL_SET_MODEM_CONTROL</b> requests are used primarily for hardware testing. No standard register layout is defined for the modem control operations. Peripheral drivers that use these IOCTLs risk making themselves dependent on the hardware features of a particular serial controller.

For an example layout of a modem control register, see the definition of the MCR bits (SERIAL_MCR_DTR through SERIAL_MCR_LOOP) in the Serial.h header file in the <a href="https://go.microsoft.com/fwlink/p/?LinkId=617962">Serial driver sample</a> on GitHub.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddser/ni-ntddser-ioctl_serial_set_modem_control">IOCTL_SERIAL_SET_MODEM_CONTROL</a>
 

 

