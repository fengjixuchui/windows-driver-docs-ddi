---
UID: NC:usbbusif.PUSB_BUSIFFN_QUERY_CONTROLLER_TYPE
title: PUSB_BUSIFFN_QUERY_CONTROLLER_TYPE (usbbusif.h)
description: The QueryControllerType routine gets information about the USB host controller to which the USB device is attached.
old-location: buses\querycontrollertype.htm
tech.root: usbref
ms.assetid: a3155544-cfb6-41a6-9d75-82618f7c7a48
ms.date: 05/07/2018
ms.keywords: PUSB_BUSIFFN_QUERY_CONTROLLER_TYPE, QueryControllerType, QueryControllerType callback function [Buses], USB_BUSIFFN_QUERY_CONTROLLER_TYPE, USB_BUSIFFN_QUERY_CONTROLLER_TYPE callback, buses.querycontrollertype, usbbusif/QueryControllerType
ms.topic: callback
req.header: usbbusif.h
req.include-header: Usbbusif.h
req.target-type: Desktop
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
req.irql: "< = DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- usbbusif.h
api_name:
- QueryControllerType
product:
- Windows
targetos: Windows
req.typenames: 
---

# PUSB_BUSIFFN_QUERY_CONTROLLER_TYPE callback function


## -description


The <b>QueryControllerType</b> routine gets information about the USB host controller to which the USB device is attached. 


## -parameters












#### - BusContext [in]

Handle returned in the <b>BusContext</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbbusif/ns-usbbusif-_usb_bus_interface_usbdi_v3">USB_BUS_INTERFACE_USBDI_V3</a> structure by an IRP_MN_QUERY_INTERFACE request.


#### - HcdiOptionFlags [out]

Reserved. Do not use.


#### - PciClass [out]

Pointer to a UCHAR variable that receives the PCI class for the USB host controller.


#### - PciDeviceId [out]

Pointer to a USHORT variable that  receives the PCI device ID for the USB host controller.


#### - PciProgIf [out]

Pointer to a UCHAR variable that receives the PCI programming interface  for the USB host controller.


#### - PciRevisionId [out]

Pointer to a UCHAR variable that receives the PCI revision number for the USB host controller.


#### - PciSubClass [out]

Pointer to a UCHAR variable that receives the PCI subclass  for the USB host controller.


#### - PciVendorId [out]

Pointer to a USHORT variable that  receives the PCI vendor ID for the USB host controller.


## -returns



Returns STATUS_SUCCESS on success, and the appropriate error code on failure. 




## -remarks



<i>PciClass</i> is typically set to PCI_CLASS_SERIAL_BUS_CTLR (0x0C).


<i>PciSubClass</i> is typically set to PCI_SUBCLASS_SB_USB (0x03).


<i>PciProgif</i> is typically set to one of the following values:
	

0x00 - Universal Host Controller Interface (UHCI)


	0x10 - Open Host Controller Interface (OHCI)
	

0x20 - Enhanced Host Controller Interface (EHCI)


The function definition that is provided on this reference page is an example function whose parameters are just placeholder names. The actual prototype of the function is declared in usbbusif.h as follows:



<pre class="syntax" xml:space="preserve"><code>typedef NTSTATUS
  (USB_BUSIFFN *PUSB_BUSIFFN_QUERY_CONTROLLER_TYPE) (
    IN PVOID,
    OUT PULONG,
    OUT PUSHORT,
    OUT PUSHORT,
    OUT PUCHAR,
    OUT PUCHAR,
    OUT PUCHAR,
    OUT PUCHAR
</code></pre>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbbusif/ns-usbbusif-_usb_bus_interface_usbdi_v3">USB_BUS_INTERFACE_USBDI_V3</a>
 

 

