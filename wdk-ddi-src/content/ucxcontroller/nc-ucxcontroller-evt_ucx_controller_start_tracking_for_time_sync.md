---
UID: NC:ucxcontroller.EVT_UCX_CONTROLLER_START_TRACKING_FOR_TIME_SYNC
title: EVT_UCX_CONTROLLER_START_TRACKING_FOR_TIME_SYNC (ucxcontroller.h)
description: UCX invokes this callback function to the start time tracking functionality in the controller.
old-location: buses\evt_ucx_controller_start_tracking_for_time_sync.htm
tech.root: usbref
ms.assetid: 8465B255-E36E-481D-B063-597B9C861DCD
ms.date: 05/07/2018
keywords: ["EVT_UCX_CONTROLLER_START_TRACKING_FOR_TIME_SYNC callback function"]
ms.keywords: EVT_UCX_CONTROLLER_START_TRACKING_FOR_TIME_SYNC, EVT_UCX_CONTROLLER_START_TRACKING_FOR_TIME_SYNC callback, EvUcxControllerStartTrackingForTimeSync, EvUcxControllerStartTrackingForTimeSync callback function [Buses], buses.evt_ucx_controller_start_tracking_for_time_sync, ucxcontroller/EvUcxControllerStartTrackingForTimeSync
f1_keywords:
 - "ucxcontroller/EvUcxControllerStartTrackingForTimeSync"
 - "EvUcxControllerStartTrackingForTimeSync"
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ucxcontroller.h
api_name:
- EvUcxControllerStartTrackingForTimeSync
targetos: Windows
req.typenames: 
---

# EVT_UCX_CONTROLLER_START_TRACKING_FOR_TIME_SYNC callback function


## -description


UCX invokes this callback function to the start time tracking functionality in the controller. 


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a> method.


### -param WdfRequest [in]

A framework request object that contains the request to start time tracking.


### -param OutputBufferLength [in]

The length, in bytes, of the request's output buffer, if an output buffer
        is available. This value is the size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_start_tracking_for_time_sync_information">USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION</a> structure. 


### -param InputBufferLength [in]

The length, in bytes, of the request's input buffer, if an input buffer
        is available. This value is the size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_start_tracking_for_time_sync_information">USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION</a> structure.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_start_tracking_for_time_sync">IOCTL_USB_START_TRACKING_FOR_TIME_SYNC</a>
 

 

