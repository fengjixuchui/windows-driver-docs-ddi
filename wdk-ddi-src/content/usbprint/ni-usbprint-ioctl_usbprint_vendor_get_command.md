---
UID: NI:usbprint.IOCTL_USBPRINT_VENDOR_GET_COMMAND
title: IOCTL_USBPRINT_VENDOR_GET_COMMAND (usbprint.h)
description: The IOCTL_USBPRINT_VENDOR_GET_COMMAND request allows upper-layer software (such as a language monitor), to issue a vendor-specific GET command to the target device.
old-location: print\ioctl_usbprint_vendor_get_command.htm
tech.root: print
ms.assetid: d4e0220b-2efb-4a24-b80a-23225b06dc66
ms.date: 04/20/2018
keywords: ["IOCTL_USBPRINT_VENDOR_GET_COMMAND IOCTL"]
ms.keywords: IOCTL_USBPRINT_VENDOR_GET_COMMAND, IOCTL_USBPRINT_VENDOR_GET_COMMAND control, IOCTL_USBPRINT_VENDOR_GET_COMMAND control code [Print Devices], print.ioctl_usbprint_vendor_get_command, usbioctl_edd39494-a6bb-4e28-a059-7c7884626105.xml, usbprint/IOCTL_USBPRINT_VENDOR_GET_COMMAND
f1_keywords:
 - "usbprint/IOCTL_USBPRINT_VENDOR_GET_COMMAND"
 - "IOCTL_USBPRINT_VENDOR_GET_COMMAND"
req.header: usbprint.h
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
- usbprint.h
api_name:
- IOCTL_USBPRINT_VENDOR_GET_COMMAND
targetos: Windows
req.typenames: 
---

# IOCTL_USBPRINT_VENDOR_GET_COMMAND IOCTL


## -description


The <b>IOCTL_USBPRINT_VENDOR_GET_COMMAND</b> request allows upper-layer software (such as a language monitor), to issue a vendor-specific GET command to the target device.


## -ioctlparameters




### -input-buffer

A pointer to a buffer, an array of UCHAR elements. The meaning of each array element is shown in the following table.

<table>
<tr>
<th>Array Element</th>
<th>Contents</th>
</tr>
<tr>
<td>
<i>lpOutBuffer</i>[0]

</td>
<td>
Vendor request code 

</td>
</tr>
<tr>
<td>
<i>lpOutBuffer</i>[1]

</td>
<td>
Vendor request value (most significant byte)

</td>
</tr>
<tr>
<td>
<i>lpOutBuffer</i>[2]

</td>
<td>
Vendor request value (least significant byte)

</td>
</tr>
</table>
 


### -input-buffer-length

The size of the input buffer, in bytes.


### -output-buffer

The output buffer, which is interpreted as an array of bytes. 


### -output-buffer-length

The size of the output buffer, in bytes.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbprint/ni-usbprint-ioctl_usbprint_vendor_set_command">IOCTL_USBPRINT_VENDOR_SET_COMMAND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

