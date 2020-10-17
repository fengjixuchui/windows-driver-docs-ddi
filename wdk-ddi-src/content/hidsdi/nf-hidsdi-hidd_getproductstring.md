---
UID: NF:hidsdi.HidD_GetProductString
title: HidD_GetProductString function (hidsdi.h)
description: The HidD_GetProductString routine returns the embedded string of a top-level collection that identifies the manufacturer's product.
old-location: hid\hidd_getproductstring.htm
tech.root: hid
ms.assetid: c0627fbf-4b64-4530-8c0f-45326a83f765
ms.date: 06/19/2019
keywords: ["HidD_GetProductString function"]
ms.keywords: HidD_GetProductString, HidD_GetProductString routine [Human Input Devices], hid.hidd_getproductstring, hidfunc_4909c6a7-11b7-489c-915c-889ad3124231.xml, hidsdi/HidD_GetProductString
req.header: hidsdi.h
req.include-header: Hidsdi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
req.lib: Hid.lib
req.dll: Hid.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - HidD_GetProductString
 - hidsdi/HidD_GetProductString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Hid.dll
api_name:
 - HidD_GetProductString
---

# HidD_GetProductString function


## -description

The <b>HidD_GetProductString</b> routine returns the embedded string of a <a href="/windows-hardware/drivers/hid/top-level-collections">top-level collection</a> that identifies the manufacturer's product.

## -parameters

### -param HidDeviceObject 

[in]
Specifies an open handle to a top-level collection.

### -param Buffer 

[out]
Pointer to a caller-allocated buffer that the routine uses to return the requested product string. The routine returns a NULL-terminated wide character string.

### -param BufferLength 

[in]
Specifies the length, in bytes, of a caller-allocated buffer provided at <i>Buffer</i>. If the buffer is not large enough to return the entire NULL-terminated embedded string, the routine returns nothing in the buffer.

## -returns

<b>HidD_GetProductString</b> returns <b>TRUE</b> if it successfully returns the entire NULL-terminated embedded string. Otherwise, the routine returns <b>FALSE</b>. Use [**GetLastError**](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) to get extended error information.

## -remarks

Only user-mode applications can call <b>HidD_GetProductString</b>. Kernel-mode drivers can use an <a href="/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_product_string">IOCTL_HID_GET_PRODUCT_STRING</a> request.

The maximum possible number of characters in an embedded string is device specific. For USB devices, the maximum string length is 126 wide characters (not including the terminating NULL character).

The <b>iProduct</b> member of a <a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_device_descriptor">USB_DEVICE_DESCRIPTOR</a> structure for a particular interface is set by the <a href="/windows-hardware/drivers/ddi/index">USB common class generic parent driver</a> based on the following rules:

<ul>
<li>
If the <b>iInterface</b> member of the <a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a> structure for the interface is nonzero, the <b>iProduct</b> member of the USB_DEVICE_DESCRIPTOR structure for the interface is set to the <b>iInterface</b> member of the USB_INTERFACE_DESCRIPTOR structure.

</li>
<li>
If the interface is grouped by a <a href="/windows-hardware/drivers/ddi/index">USB interface association descriptor</a>, and the <b>iFunction</b> member of the interface association descriptor for the interface is nonzero, the <b>iProduct</b> member of the USB_DEVICE_DESCRIPTOR structure for the interface is set to the <b>iFunction</b> member of the interface association descriptor.

</li>
</ul>
For more information, see <a href="/windows-hardware/drivers/hid/hid-collections">HID Collections</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getindexedstring">HidD_GetIndexedString</a>



<a href="/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getphysicaldescriptor">HidD_GetPhysicalDescriptor</a>



<a href="/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getserialnumberstring">HidD_GetSerialNumberString</a>



<a href="/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_indexed_string">IOCTL_HID_GET_INDEXED_STRING</a>



<a href="/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_manufacturer_string">IOCTL_HID_GET_MANUFACTURER_STRING</a>



<a href="/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_product_string">IOCTL_HID_GET_PRODUCT_STRING</a>



<a href="/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_serialnumber_string">IOCTL_HID_GET_SERIALNUMBER_STRING</a>