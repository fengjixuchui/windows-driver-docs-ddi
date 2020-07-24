---
UID: NF:udecxusbdevice.UdecxUsbDeviceInitAddDescriptorWithIndex
title: UdecxUsbDeviceInitAddDescriptorWithIndex function (udecxusbdevice.h)
description: Adds a USB descriptor to the initialization parameters used to create a virtual USB device.
old-location: buses\udecxusbdeviceinitadddescriptorwithindex.htm
tech.root: usbref
ms.assetid: 96DF01F1-2584-4152-8EB9-D2515CA42B03
ms.date: 05/07/2018
keywords: ["UdecxUsbDeviceInitAddDescriptorWithIndex function"]
ms.keywords: UdecxUsbDeviceInitAddDescriptorWithIndex, UdecxUsbDeviceInitAddDescriptorWithIndex function [Buses], buses.udecxusbdeviceinitadddescriptorwithindex, udecxusbdevice/UdecxUsbDeviceInitAddDescriptorWithIndex
f1_keywords:
 - "udecxusbdevice/UdecxUsbDeviceInitAddDescriptorWithIndex"
 - "UdecxUsbDeviceInitAddDescriptorWithIndex"
req.header: udecxusbdevice.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Udecxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Udecxstub.lib
- Udecxstub.dll
api_name:
- UdecxUsbDeviceInitAddDescriptorWithIndex
targetos: Windows
req.typenames: 
---

# UdecxUsbDeviceInitAddDescriptorWithIndex function


## -description


Adds a USB descriptor to the initialization parameters used to create a virtual USB device.


## -parameters




### -param UdecxUsbDeviceInit [in, out]

A pointer to a WDF-allocated structure that contains initialization parameters for the virtual USB device.  The client driver retrieved this pointer in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdeviceinitallocate">UdecxUsbDeviceInitAllocate</a>. 


### -param Descriptor [in]

A caller-allocated buffer that contains the USB descriptor to add to the device.


### -param DescriptorLength [in]

The length of the descriptor buffer.


### -param DescriptorIndex [in]

The index of the descriptor.


## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">USB String Descriptors</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdeviceinitallocate">UdecxUsbDeviceInitAllocate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
 

 

