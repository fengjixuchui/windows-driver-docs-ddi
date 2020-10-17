---
UID: NF:udecxwdfdevice.UdecxWdfDeviceAddUsbDeviceEmulation
title: UdecxWdfDeviceAddUsbDeviceEmulation function (udecxwdfdevice.h)
description: Initializes a framework device object to support operations related to a host controller and a virtual USB device attached to the controller.
old-location: buses\udecxwdfdeviceaddusbdeviceemulation.htm
tech.root: usbref
ms.assetid: EE7644A9-AA57-4C53-9FA5-F844F2BFB0D7
ms.date: 05/07/2018
keywords: ["UdecxWdfDeviceAddUsbDeviceEmulation function"]
ms.keywords: UdecxWdfDeviceAddUsbDeviceEmulation, UdecxWdfDeviceAddUsbDeviceEmulation function [Buses], buses.udecxwdfdeviceaddusbdeviceemulation, udecxwdfdevice/UdecxWdfDeviceAddUsbDeviceEmulation
req.header: udecxwdfdevice.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - UdecxWdfDeviceAddUsbDeviceEmulation
 - udecxwdfdevice/UdecxWdfDeviceAddUsbDeviceEmulation
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Udecxstub.lib
 - Udecxstub.dll
api_name:
 - UdecxWdfDeviceAddUsbDeviceEmulation
---

# UdecxWdfDeviceAddUsbDeviceEmulation function


## -description

Initializes a framework device object to support operations related to a host controller and a virtual USB device attached to the controller.

## -parameters

### -param WdfDevice

<p>A handle to the framework device object that the client driver retrieved in the previous call to <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate"><b>WdfDeviceCreate</b></a>.</p>

### -param Config 

[in]
 A pointer to a <a href="/windows-hardware/drivers/ddi/udecxwdfdevice/ns-udecxwdfdevice-_udecx_wdf_device_config">UDECX_WDF_DEVICE_CONFIG</a> structure that the client driver initialized by calling <a href="/windows-hardware/drivers/ddi/udecxwdfdevice/nf-udecxwdfdevice-udecx_wdf_device_config_init">UDECX_WDF_DEVICE_CONFIG_INIT</a>.

## -returns

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.

## -remarks

The UDE client driver for the emulated host controller and the USB device must call this method after the <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a> call. 

During this call, the client driver-supplied event callback implementations are also registered. Supply function  pointers to those functions by call setting appropriate members of <a href="/windows-hardware/drivers/ddi/udecxwdfdevice/ns-udecxwdfdevice-_udecx_wdf_device_config">UDECX_WDF_DEVICE_CONFIG</a>. 

The method makes the framework device object capable of performing operations related to a controller and its root hub, such as handling various queues required to process IOCTL requests sent to the attached USB device.

## -see-also

<a href="/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>