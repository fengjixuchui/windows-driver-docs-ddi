---
UID: NS:udecxwdfdevice._UDECX_WDF_DEVICE_CONFIG
title: _UDECX_WDF_DEVICE_CONFIG (udecxwdfdevice.h)
description: Contains pointers to event callback functions implemented by the UDE client driver for a USB host controller. Initialize this structure by calling UDECX_WDF_DEVICE_CONFIG_INIT.
old-location: buses\udecx_wdf_device_config.htm
tech.root: usbref
ms.assetid: 54853C39-FA6C-4F9B-A202-F116C43D3A4E
ms.date: 05/07/2018
keywords: ["UDECX_WDF_DEVICE_CONFIG structure"]
ms.keywords: "*PUDECX_WDF_DEVICE_CONFIG, PUDECX_WDF_DEVICE_CONFIG, PUDECX_WDF_DEVICE_CONFIG structure pointer [Buses], UDECX_WDF_DEVICE_CONFIG, UDECX_WDF_DEVICE_CONFIG structure [Buses], _UDECX_WDF_DEVICE_CONFIG, buses.udecx_wdf_device_config, udecxwdfdevice/PUDECX_WDF_DEVICE_CONFIG, udecxwdfdevice/UDECX_WDF_DEVICE_CONFIG"
req.header: udecxwdfdevice.h
req.include-header: Udecx.h
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
targetos: Windows
req.typenames: UDECX_WDF_DEVICE_CONFIG, *PUDECX_WDF_DEVICE_CONFIG
f1_keywords:
 - _UDECX_WDF_DEVICE_CONFIG
 - udecxwdfdevice/_UDECX_WDF_DEVICE_CONFIG
 - PUDECX_WDF_DEVICE_CONFIG
 - udecxwdfdevice/PUDECX_WDF_DEVICE_CONFIG
 - UDECX_WDF_DEVICE_CONFIG
 - udecxwdfdevice/UDECX_WDF_DEVICE_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - udecxwdfdevice.h
api_name:
 - UDECX_WDF_DEVICE_CONFIG
---

# _UDECX_WDF_DEVICE_CONFIG structure


## -description

Contains pointers to event callback functions implemented by the UDE client driver for a USB host controller. Initialize this structure by calling <a href="/windows-hardware/drivers/ddi/udecxwdfdevice/nf-udecxwdfdevice-udecx_wdf_device_config_init">UDECX_WDF_DEVICE_CONFIG_INIT</a>.

## -struct-fields

### -field Size

The size of this structure.

### -field NumberOfUsb20Ports

The number of USB 2.0 ports on the root hub of the emulated host controller.

### -field NumberOfUsb30Ports

The number of USB 3.0 ports on the root hub of the emulated host controller.

### -field EvtUdecxWdfDeviceQueryUsbCapability

A pointer to an <a href="/windows-hardware/drivers/ddi/udecxwdfdevice/nc-udecxwdfdevice-evt_udecx_wdf_device_query_usb_capability">EVT_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY</a> callback function.

### -field ResetAction

A <a href="/windows-hardware/drivers/ddi/udecxwdfdevice/ne-udecxwdfdevice-_udecx_wdf_device_reset_action">UDECX_WDF_DEVICE_RESET_ACTION</a>-type value that indicates the reset action: each attached device or the host controller.

### -field EvtUdecxWdfDeviceReset

A pointer to an <a href="/windows-hardware/drivers/ddi/udecxwdfdevice/nc-udecxwdfdevice-evt_udecx_wdf_device_reset">EVT_UDECX_WDF_DEVICE_RESET</a> callback function.

## -see-also

<a href="/windows-hardware/drivers/ddi/udecxwdfdevice/nf-udecxwdfdevice-udecx_wdf_device_config_init">UDECX_WDF_DEVICE_CONFIG_INIT</a>



<a href="/windows-hardware/drivers/ddi/udecxwdfdevice/nf-udecxwdfdevice-udecxwdfdeviceaddusbdeviceemulation">UdecxWdfDeviceAddUsbDeviceEmulation</a>