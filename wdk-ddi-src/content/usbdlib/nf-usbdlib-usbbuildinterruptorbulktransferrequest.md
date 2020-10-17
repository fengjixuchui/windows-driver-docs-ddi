---
UID: NF:usbdlib.UsbBuildInterruptOrBulkTransferRequest
title: UsbBuildInterruptOrBulkTransferRequest macro (usbdlib.h)
description: The UsbBuildInterruptOrBulkTransferRequest macro formats an URB to send or receive data on a bulk pipe, or to receive data from an interrupt pipe.
old-location: buses\usbbuildinterruptorbulktransferrequest.htm
tech.root: usbref
ms.assetid: 2500fa22-b3f9-419d-9e37-5060b83403fb
ms.date: 05/07/2018
keywords: ["UsbBuildInterruptOrBulkTransferRequest macro"]
ms.keywords: UsbBuildInterruptOrBulkTransferRequest, UsbBuildInterruptOrBulkTransferRequest routine [Buses], buses.usbbuildinterruptorbulktransferrequest, usbdlib/UsbBuildInterruptOrBulkTransferRequest, usbfunc_ecc1d157-942d-4d0e-9c07-9fef00cd5faf.xml
req.header: usbdlib.h
req.include-header: Usbdlib.h
req.target-type: Desktop
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
 - UsbBuildInterruptOrBulkTransferRequest
 - usbdlib/UsbBuildInterruptOrBulkTransferRequest
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbdlib.h
api_name:
 - UsbBuildInterruptOrBulkTransferRequest
---

# UsbBuildInterruptOrBulkTransferRequest macro


## -description

The <b>UsbBuildInterruptOrBulkTransferRequest</b> macro formats an <a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> to send or receive data on a bulk pipe, or to receive data from an interrupt pipe.

## -parameters

### -param urb 

[in, out]
Pointer to an <a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> to be formatted as an interrupt or bulk transfer request.

### -param length 

[in]
Specifies the size, in bytes, of the <a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a>.

### -param pipeHandle 

[in]
Specifies the handle for this pipe returned by the HCD when a configuration was selected.

### -param transferBuffer 

[in, optional]
Pointer to a resident buffer for the transfer or is <b>NULL</b> if an MDL is supplied in <i>TransferBufferMDL</i>. The contents of this buffer depend on the value of <i>TransferFlags</i>. If USBD_TRANSFER_DIRECTION_IN is specified, this buffer will contain data read from the device on return from the HCD. Otherwise, this buffer contains driver-supplied data to be transferred to the device.

### -param transferBufferMDL 

[in, optional]
Pointer to an MDL that describes a resident buffer or is <b>NULL</b> if a buffer is supplied in <i>TransferBuffer</i>. The contents of the buffer depend on the value of <i>TransferFlags</i>. If USBD_TRANSFER_DIRECTION_IN is specified, the described buffer will contain data read from the device on return from the HCD. Otherwise, the buffer contains driver-supplied data to be transferred to the device. The MDL must be allocated from nonpaged pool.

### -param transferBufferLength 

[in]
Specifies the length, in bytes, of the buffer specified in <i>TransferBuffer</i> or described in <i>TransferBufferMDL</i>.

### -param transferFlags 

[in]
Specifies zero, one, or a combination of the following flags:





#### USBD_TRANSFER_DIRECTION_IN

Is set to request data from a device. To transfer data to a device, this flag must be clear.



#### USBD_SHORT_TRANSFER_OK

Can be used if USBD_TRANSFER_DIRECTION_IN is set. If set, directs the HCD not to return an error if a packet is received from the device that is shorter than the maximum packet size for the endpoint. Otherwise, a short request returns an error condition.

### -param link 

[in]
Reserved. Must be set to <b>NULL</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a>



<a href="/windows-hardware/drivers/ddi/_usbref/">USB device driver programming reference</a>



<a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_device_descriptor">USB_DEVICE_DESCRIPTOR</a>