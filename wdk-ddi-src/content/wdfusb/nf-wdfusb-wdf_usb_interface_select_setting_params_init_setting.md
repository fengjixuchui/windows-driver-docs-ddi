---
UID: NF:wdfusb.WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING
title: WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING function (wdfusb.h)
description: The WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING function initializes a WDF_USB_INTERFACE_SELECT_SETTING_PARAMS structure so that a driver can select a USB interface by specifying a handle to an interface object and an alternate setting for the interface.
old-location: wdf\wdf_usb_interface_select_setting_params_init_setting.htm
tech.root: wdf
ms.assetid: 2b58eb8f-c468-4bc6-ad50-0bc9f2dee561
ms.date: 02/26/2018
keywords: ["WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING function"]
ms.keywords: DFUsbRef_9f764089-ac6f-404a-8196-170547e40495.xml, WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING, WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING function, kmdf.wdf_usb_interface_select_setting_params_init_setting, wdf.wdf_usb_interface_select_setting_params_init_setting, wdfusb/WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
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
req.typenames: 
f1_keywords:
 - WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING
 - wdfusb/WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfusb.h
api_name:
 - WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING
---

# WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING</b> function initializes a <a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_interface_select_setting_params">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure so that a driver can select a USB interface by specifying a handle to an interface object and an alternate setting for the interface.

## -parameters

### -param Params 

[out]
A pointer to a driver-allocated <a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_interface_select_setting_params">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure.

### -param SettingIndex 

[in]
An index value that identifies an alternate setting for the interface. (The interface is identified by an interface object handle that the driver passes to <a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfaceselectsetting">WdfUsbInterfaceSelectSetting</a>.)

## -remarks

The <b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING</b> function zeros the <a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_interface_select_setting_params">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure and sets its <b>Size</b> member to the size of the structure. It also sets the <b>Type</b> member to <b>WdfUsbInterfaceSelectSettingTypeSetting</b> and sets the <b>Types.Interface.SettingIndex</b> member to the value that is specified by <i>SettingIndex</i>.

To initialize a <a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_interface_select_setting_params">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a> structure, your driver must call one of the following functions:

<ul>
<li>

<a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_interface_select_setting_params_init_descriptor">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR</a>


</li>
<li>
<b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING</b>

</li>
<li>

<a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_interface_select_setting_params_init_urb">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB</a>


</li>
</ul>
For a code example that uses <b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING</b>, see <a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfaceselectsetting">WdfUsbInterfaceSelectSetting</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_interface_select_setting_params">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</a>



<a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_interface_select_setting_params_init_descriptor">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_interface_select_setting_params_init_urb">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB</a>



<a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfaceselectsetting">WdfUsbInterfaceSelectSetting</a>