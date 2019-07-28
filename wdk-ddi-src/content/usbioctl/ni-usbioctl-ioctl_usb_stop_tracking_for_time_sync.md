---
UID: NI:usbioctl.IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC
title: IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC (usbioctl.h)
description: This request unegisters the caller with USB driver stack for time sync services.
old-location: buses\_ioctl_usb_stop_tracking_for_time_sync.htm
tech.root: usbref
ms.assetid: 232AC14B-CE3C-44AC-9428-5594993CD749
ms.date: 05/07/2018
ms.keywords: IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC, IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC control, IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC control code [Buses], buses._ioctl_usb_stop_tracking_for_time_sync, usbioctl/ IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC
ms.topic: ioctl
f1_keywords:
 - "usbioctl/IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC"
req.header: usbioctl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Usbioctl.h
api_name:
- IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC IOCTL


## -description


This request unegisters the caller with USB driver stack for time sync services. 


## -ioctlparameters




### -input-buffer

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbioctl/ns-usbioctl-_usb_stop_tracking_for_time_sync_information">USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION</a> structure that contains the time tracking handle previously received through the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbioctl/ni-usbioctl-ioctl_usb_start_tracking_for_time_sync">IOCTL_USB_START_TRACKING_FOR_TIME_SYNC</a> request.


### -input-buffer-length

The size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbioctl/ns-usbioctl-_usb_stop_tracking_for_time_sync_information">USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION</a> structure.


### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> indicates an the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

