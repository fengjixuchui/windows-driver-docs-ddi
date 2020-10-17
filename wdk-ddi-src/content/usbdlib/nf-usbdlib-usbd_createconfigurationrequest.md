---
UID: NF:usbdlib.USBD_CreateConfigurationRequest
title: USBD_CreateConfigurationRequest function (usbdlib.h)
description: The USBD_CreateConfigurationRequest routine has been deprecated. Use USBD_CreateConfigurationRequestEx instead.
old-location: buses\usbd_createconfigurationrequest.htm
tech.root: usbref
ms.assetid: e1f397f6-2f33-4352-9bbc-2b2a49dcd067
ms.date: 05/07/2018
keywords: ["USBD_CreateConfigurationRequest function"]
ms.keywords: USBD_CreateConfigurationRequest, USBD_CreateConfigurationRequest routine [Buses], buses.usbd_createconfigurationrequest, usbdlib/USBD_CreateConfigurationRequest, usbfunc_d2701cb6-8159-48e0-b668-bb3b02226a7d.xml
req.header: usbdlib.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Deprecated. Use USBD_CreateConfigurationRequestEx instead.
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
req.lib: Usbd.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - USBD_CreateConfigurationRequest
 - usbdlib/USBD_CreateConfigurationRequest
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Usbd.lib
 - Usbd.dll
api_name:
 - USBD_CreateConfigurationRequest
---

# USBD_CreateConfigurationRequest function


## -description

The  <b>USBD_CreateConfigurationRequest</b> routine has been deprecated. Use <a href="/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_createconfigurationrequestex">USBD_CreateConfigurationRequestEx</a> instead.

## -parameters

### -param ConfigurationDescriptor 

[in]
Pointer to a caller-allocated <a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_configuration_descriptor">USB_CONFIGURATION_DESCRIPTOR</a> structure that contains the configuration descriptor for the configuration to be selected.

### -param Siz 

[in, out]
Size of the <a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> structure.

## -returns

<b>USBD_CreateConfigurationRequest</b> allocates a <a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> structure, formats it for the URB_FUNCTION_SELECT_CONFIGURATION request (select-configuration request), and returns a pointer to the <b>URB</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/_usbref/">USB device driver programming reference</a>



<a href="/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_createconfigurationrequestex">USBD_CreateConfigurationRequestEx</a>