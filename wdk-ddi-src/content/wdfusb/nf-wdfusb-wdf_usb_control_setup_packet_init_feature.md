---
UID: NF:wdfusb.WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE
title: WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE function (wdfusb.h)
description: The WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE function initializes a WDF_USB_CONTROL_SETUP_PACKET structure for a USB control transfer that sets or clears a device feature.
old-location: wdf\wdf_usb_control_setup_packet_init_feature.htm
tech.root: wdf
ms.assetid: ef3f7b9f-8b4b-4d47-8457-17452e3e918a
ms.date: 02/26/2018
keywords: ["WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE function"]
ms.keywords: DFUsbRef_becbf646-e647-4337-a1cb-05a72c3dd215.xml, WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE, WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE function, kmdf.wdf_usb_control_setup_packet_init_feature, wdf.wdf_usb_control_setup_packet_init_feature, wdfusb/WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE
f1_keywords:
 - "wdfusb/WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfusb.h
api_name:
- WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE</b> function initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a> structure for a USB control transfer that sets or clears a device feature.


## -parameters




### -param Packet [out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a> structure.


### -param BmRequestRecipient [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ne-wdfusb-_wdf_usb_bmrequest_recipient">WDF_USB_BMREQUEST_RECIPIENT</a>-typed value that is stored in the <b>Packet.bm.Request.Recipient</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a> structure. 


### -param FeatureSelector [in]

A feature-specific value that is stored in the <b>Packet.wValue.Value</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a> structure.


### -param Index [in]

A feature-specific index value that is stored in the <b>Packet.wIndex.Value</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a> structure.


### -param SetFeature [in]

A Boolean value that, if <b>TRUE</b>, indicates that the specified feature will be set. If <b>FALSE</b>, the specified feature will be cleared.


## -remarks



The <b>WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE</b> function does the following:

<ol>
<li>
Zeros the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a> structure.

</li>
<li>
Sets the <b>Packet.bm.Request.Type</b> member to <b>BmRequestStandard</b>.

</li>
<li>
Sets the <b>Packet.bm.Request.Dir</b> member to <b>BmRequestDeviceToDevice</b>.

</li>
<li>
Sets the <b>Packet.bRequest</b> member to either a "set feature" or a "clear feature" request value, based on the <i>SetFeature</i> argument.

</li>
<li>
Sets other structure members by using the <b>WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE</b> function's input arguments.

</li>
</ol>
To initialize a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a> structure, the driver should call one of the following functions:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_control_setup_packet_init">WDF_USB_CONTROL_SETUP_PACKET_INIT</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_control_setup_packet_init_class">WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS</a>


</li>
<li>
<b>WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE</b>

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_control_setup_packet_init_get_status">WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_control_setup_packet_init_vendor">WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR</a>


</li>
</ul>

#### Examples

The following code example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a> structure.

```cpp
WDF_USB_CONTROL_SETUP_PACKET packet;

WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE(
                                          &packet,
                                          BMREQUEST_TO_DEVICE,
                                          USB_DEVICE_DESCRIPTOR_TYPE,
                                          0,
                                          FALSE
                                          );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ne-wdfusb-_wdf_usb_bmrequest_recipient">WDF_USB_BMREQUEST_RECIPIENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_control_setup_packet_init">WDF_USB_CONTROL_SETUP_PACKET_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_control_setup_packet_init_class">WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_control_setup_packet_init_get_status">WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_control_setup_packet_init_vendor">WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR</a>
 

 

