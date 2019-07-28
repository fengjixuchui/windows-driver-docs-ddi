---
UID: NF:wdfusb.WdfUsbTargetDeviceResetPortSynchronously
title: WdfUsbTargetDeviceResetPortSynchronously function (wdfusb.h)
description: The WdfUsbTargetDeviceResetPortSynchronously method resets the USB port that is associated with the specified USB device.
old-location: wdf\wdfusbtargetdeviceresetportsynchronously.htm
tech.root: wdf
ms.assetid: 4f0941ea-ccbb-4345-82c0-ec5d88862b05
ms.date: 02/26/2018
ms.keywords: DFUsbRef_423196d9-8f58-462a-91b3-9d747a12d6df.xml, WdfUsbTargetDeviceResetPortSynchronously, WdfUsbTargetDeviceResetPortSynchronously method, kmdf.wdfusbtargetdeviceresetportsynchronously, wdf.wdfusbtargetdeviceresetportsynchronously, wdfusb/WdfUsbTargetDeviceResetPortSynchronously
ms.topic: function
f1_keywords:
 - "wdfusb/WdfUsbTargetDeviceResetPortSynchronously"
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfUsbTargetDeviceResetPortSynchronously
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetDeviceResetPortSynchronously function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbTargetDeviceResetPortSynchronously</b> method resets the USB port that is associated with the specified USB device.


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>.


## -returns



<b>WdfUsbTargetDeviceResetPortSynchronously</b> returns the USB I/O target's completion status value if the operation succeeds. Otherwise, this method can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The caller's IRQL was invalid.

</td>
</tr>
</table>
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfUsbTargetDeviceResetPortSynchronously</b> method resets the USB port by sending an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbioctl/ni-usbioctl-ioctl_internal_usb_reset_port">IOCTL_INTERNAL_USB_RESET_PORT</a> request.

Before the framework resets the I/O target's USB port, it cancels all I/O requests that remain in the I/O target's queue. The driver must not send additional I/O requests to the I/O target until <b>WdfUsbTargetDeviceResetPortSynchronously</b> returns.

The driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetstop">WdfIoTargetStop</a> before it calls <b>WdfUsbTargetDeviceResetPortSynchronously</b>. After <b>WdfUsbTargetDeviceResetPortSynchronously</b> returns, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetstart">WdfIoTargetStart</a>.

After a successful reset operation, the bus driver reselects the configuration and any alternate interface settings that the device had before the reset operation occurred.

For more information about the <b>WdfUsbTargetDeviceResetPortSynchronously</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example resets a specified device's USB port.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS status;

status = WdfUsbTargetDeviceResetPortSynchronously(UsbDevice);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>
 

 

