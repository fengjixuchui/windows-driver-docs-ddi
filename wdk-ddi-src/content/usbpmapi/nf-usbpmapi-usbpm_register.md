---
UID: NF:usbpmapi.UsbPm_Register
title: UsbPm_Register function (usbpmapi.h)
description: Registers the client driver with the Policy Manager to report hub arrival/removal and connector state changes.
ms.assetid: 6560279e-9174-49ba-9a59-341baec7494a
ms.date: 09/30/2018
keywords: ["UsbPm_Register function"]
ms.keywords: UsbPm_Register
tech.root: usbref
req.header: usbpmapi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: 2.27
req.lib: UsbPmApi.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
f1_keywords:
 - UsbPm_Register
 - usbpmapi/UsbPm_Register
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - UsbPmApi.lib
api_name:
 - UsbPm_Register
---

# UsbPm_Register function


## -description

Registers the client driver with the Policy Manager to report hub arrival/removal and connector state changes.

## -parameters

### -param ClientConfig

[In] The pointer to a caller-supplied [**USBPM_CLIENT_CONFIG**](ns-usbpmapi-_usbpm_client_config.md) structure. Initialize the structure by calling macro [**USBPM_CLIENT_CONFIG_INIT**](nf-usbpmapi-usbpm_client_config_init.md).

### -param ClientHandle

[Out] A pointer to a location that receives a handle to the registration operation.

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate [NTSTATUS](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values) value.

## -remarks

The client driver's callback functions might start getting invoked before **UsbPm_Register** returns. The _ClientHandle_ value is set to a valid value before callback functions are invoked. 

The driver typically calls **UsbPm_Register** in the driver's [**EVT_WDF_DEVICE_SELF_MANAGED_IO_INIT**](../wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_init.md) and unregisters in [**EVT_WDF_DEVICE_SELF_MANAGED_IO_CLEANUP**](../wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup.md) by calling [**UsbPm_Deregister**](nf-usbpmapi-usbpm_deregister.md).

## -see-also

