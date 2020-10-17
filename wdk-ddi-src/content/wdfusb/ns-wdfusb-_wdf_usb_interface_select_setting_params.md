---
UID: NS:wdfusb._WDF_USB_INTERFACE_SELECT_SETTING_PARAMS
title: _WDF_USB_INTERFACE_SELECT_SETTING_PARAMS (wdfusb.h)
description: The WDF_USB_INTERFACE_SELECT_SETTING_PARAMS structure contains selection information for a USB interface.
old-location: wdf\wdf_usb_interface_select_setting_params.htm
tech.root: wdf
ms.assetid: fad8a205-8427-48c5-b4b5-b125aa9fe85c
ms.date: 02/26/2018
keywords: ["WDF_USB_INTERFACE_SELECT_SETTING_PARAMS structure"]
ms.keywords: "*PWDF_USB_INTERFACE_SELECT_SETTING_PARAMS, DFUsbRef_a32b6d83-abf8-4cc6-9ce3-3d03551164a4.xml, PWDF_USB_INTERFACE_SELECT_SETTING_PARAMS, PWDF_USB_INTERFACE_SELECT_SETTING_PARAMS structure pointer, WDF_USB_INTERFACE_SELECT_SETTING_PARAMS, WDF_USB_INTERFACE_SELECT_SETTING_PARAMS structure, _WDF_USB_INTERFACE_SELECT_SETTING_PARAMS, kmdf.wdf_usb_interface_select_setting_params, wdf.wdf_usb_interface_select_setting_params, wdfusb/PWDF_USB_INTERFACE_SELECT_SETTING_PARAMS, wdfusb/WDF_USB_INTERFACE_SELECT_SETTING_PARAMS"
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
req.irql: 
targetos: Windows
req.typenames: WDF_USB_INTERFACE_SELECT_SETTING_PARAMS, *PWDF_USB_INTERFACE_SELECT_SETTING_PARAMS
f1_keywords:
 - _WDF_USB_INTERFACE_SELECT_SETTING_PARAMS
 - wdfusb/_WDF_USB_INTERFACE_SELECT_SETTING_PARAMS
 - PWDF_USB_INTERFACE_SELECT_SETTING_PARAMS
 - wdfusb/PWDF_USB_INTERFACE_SELECT_SETTING_PARAMS
 - WDF_USB_INTERFACE_SELECT_SETTING_PARAMS
 - wdfusb/WDF_USB_INTERFACE_SELECT_SETTING_PARAMS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfusb.h
api_name:
 - WDF_USB_INTERFACE_SELECT_SETTING_PARAMS
---

# _WDF_USB_INTERFACE_SELECT_SETTING_PARAMS structure


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</b> structure contains selection information for a USB interface.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Type

A <a href="/windows-hardware/drivers/ddi/wdfusb/ne-wdfusb-_wdfusbtargetdeviceselectsettingtype">WdfUsbTargetDeviceSelectSettingType</a>-typed value that identifies a technique for specifying a device interface.

### -field Types

### -field Types.Descriptor

### -field Types.Descriptor.InterfaceDescriptor

If the <b>Type</b> member is <b>WdfUsbInterfaceSelectSettingTypeDescriptor</b>, this member contains a pointer to a <a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a> structure that identifies a device interface.

### -field Types.Interface

### -field Types.Interface.SettingIndex

If the <b>Type</b> member is <b>WdfUsbInterfaceSelectSettingTypeSetting</b>, this member contains an index value that identifies an alternate setting for the interface. (The interface is identified by an interface object handle that the driver passes to <a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfaceselectsetting">WdfUsbInterfaceSelectSetting</a>.)

### -field Types.Urb

### -field Types.Urb.Urb

If the <b>Type</b> member is <b>WdfUsbInterfaceSelectSettingTypeUrb</b>, this member contains a pointer to a <a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> structure that describes a device interface. The URB structure's <b>Function</b> member must be URB_FUNCTION_SELECT_INTERFACE, and other members must be initialized as appropriate for the interface.

## -remarks

The <b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</b> structure is used as input to the <a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfaceselectsetting">WdfUsbInterfaceSelectSetting</a> method. 

To initialize a <b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</b> structure, your driver must call one of the following functions:

<ul>
<li>

<a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_interface_select_setting_params_init_descriptor">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR</a>


</li>
<li>

<a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_interface_select_setting_params_init_setting">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING</a>


</li>
<li>

<a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_interface_select_setting_params_init_urb">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB</a>


</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a>



<a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfaceselectsetting">WdfUsbInterfaceSelectSetting</a>



<a href="/windows-hardware/drivers/ddi/wdfusb/ne-wdfusb-_wdfusbtargetdeviceselectsettingtype">WdfUsbTargetDeviceSelectSettingType</a>