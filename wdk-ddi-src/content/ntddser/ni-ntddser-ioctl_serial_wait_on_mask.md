---
UID: NI:ntddser.IOCTL_SERIAL_WAIT_ON_MASK
title: IOCTL_SERIAL_WAIT_ON_MASK (ntddser.h)
description: The IOCTL_SERIAL_WAIT_ON_MASK request is used to wait for the occurrence of any wait event specified by using an IOCTL_SERIAL_SET_WAIT_MASK request.
old-location: serports\ioctl_serial_wait_on_mask.htm
tech.root: serports
ms.assetid: b813bd59-249d-4cd1-bf56-4525c7f1fa1d
ms.date: 04/23/2018
keywords: ["IOCTL_SERIAL_WAIT_ON_MASK IOCTL"]
ms.keywords: IOCTL_SERIAL_WAIT_ON_MASK, IOCTL_SERIAL_WAIT_ON_MASK control, IOCTL_SERIAL_WAIT_ON_MASK control code [Serial Ports], ntddser/IOCTL_SERIAL_WAIT_ON_MASK, serports.ioctl_serial_wait_on_mask, serref_4879eda6-26ca-48a6-9176-4aa20d46aa47.xml
f1_keywords:
 - "ntddser/IOCTL_SERIAL_WAIT_ON_MASK"
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
- IOCTL_SERIAL_WAIT_ON_MASK
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERIAL_WAIT_ON_MASK IOCTL


## -description


The <b>IOCTL_SERIAL_WAIT_ON_MASK</b> request is used to wait for the occurrence of any wait event specified by using an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_wait_mask">IOCTL_SERIAL_SET_WAIT_MASK</a> request.

A wait-on-mask request is completed after one of the following events occurs:
<ul>
<li>
A wait event occurs that was specified by the most recent set-wait-mask request.

</li>
<li>
An <b>IOCTL_SERIAL_SET_WAIT_MASK</b> request is received while a wait-on-mask request is pending. The driver completes the pending wait-on-mask request with a status of STATUS_SUCCESS and the output wait mask is set to zero.

</li>
</ul>A client can wait for the wait events represented by flag bits <b>SERIAL_EV_RXCHAR</b> through <b>SERIAL_EV_EVENT2</b>. For more information about these event flags, see <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a>.

A client sends an <b>IOCTL_SERIAL_WAIT_ON_MASK</b> request to wait for the occurrence of an event that was specified in the wait mask supplied by the most recent <b>IOCTL_SERIAL_SET_WAIT_MASK</b> request. If one or more events in the current wait mask occur before the <b>IOCTL_SERIAL_WAIT_ON_MASK</b> request is sent, this request is immediately completed with a status of STATUS_SUCCESS and an output mask value that identifies the events. If no event in the wait mask occurs before the <b>IOCTL_SERIAL_WAIT_ON_MASK</b> request is sent, this request is marked as pending, and it waits in the serial controller queue for the next occurrence of an event in the current wait mask.

After a client's <b>IOCTL_SERIAL_WAIT_ON_MASK</b> request is completed with a status of STATUS_SUCCESS and a nonzero output mask value, the client can send a new <b>IOCTL_SERIAL_WAIT_ON_MASK</b> request to wait for another event in the current wait mask. Only a new event that occurs after the previous <b>IOCTL_SERIAL_WAIT_ON_MASK</b> request was completed will cause the new <b>IOCTL_SERIAL_WAIT_ON_MASK</b> request to be completed with a status of STATUS_SUCCESS and a nonzero output mask value.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

<b>AssociatedIrp.System</b> buffer points to a ULONG buffer that holds an event wait mask. The event wait mask indicates which wait events occurred. The event wait mask is set to zero or to the bitwise-OR of one or more of the <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a> flag bits.


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a ULONG.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> member is set to the size, in bytes, of a ULONG.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>. A status of STATUS_INVALID_PARAMETER indicates that no wait events are set, or a wait-on-mask request is already pending.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_wait_mask">IOCTL_SERIAL_SET_WAIT_MASK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a>
 

 

