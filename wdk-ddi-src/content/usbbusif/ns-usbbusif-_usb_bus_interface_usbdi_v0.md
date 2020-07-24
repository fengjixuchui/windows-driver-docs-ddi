---
UID: NS:usbbusif._USB_BUS_INTERFACE_USBDI_V0
title: _USB_BUS_INTERFACE_USBDI_V0 (usbbusif.h)
description: The USB_BUS_INTERFACE_USBDI_V0 structure is provided by the USB hub driver to allow USB clients to make direct calls to the hub driver without allocating IRPs.
old-location: buses\usb_bus_interface_usbdi_v0.htm
tech.root: usbref
ms.assetid: f21ba9f4-9571-4918-8f10-97bd308c69f3
ms.date: 05/07/2018
keywords: ["_USB_BUS_INTERFACE_USBDI_V0 structure"]
ms.keywords: "*PUSB_BUS_INTERFACE_USBDI_V0, PUSB_BUS_INTERFACE_USBDI_V0, PUSB_BUS_INTERFACE_USBDI_V0 structure pointer [Buses], USB_BUS_INTERFACE_USBDI_V0, USB_BUS_INTERFACE_USBDI_V0 structure [Buses], _USB_BUS_INTERFACE_USBDI_V0, buses.usb_bus_interface_usbdi_v0, usbbusif/PUSB_BUS_INTERFACE_USBDI_V0, usbbusif/USB_BUS_INTERFACE_USBDI_V0, usbinterKR_2af580ba-2b3f-4f20-808a-5cd5d42b8ada.xml"
f1_keywords:
 - "usbbusif/USB_BUS_INTERFACE_USBDI_V0"
 - "USB_BUS_INTERFACE_USBDI_V0"
req.header: usbbusif.h
req.include-header: Usbbusif.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- usbbusif.h
api_name:
- USB_BUS_INTERFACE_USBDI_V0
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V0, *PUSB_BUS_INTERFACE_USBDI_V0
---

# _USB_BUS_INTERFACE_USBDI_V0 structure


## -description


The <b>USB_BUS_INTERFACE_USBDI_V0</b> structure is provided by the USB hub driver to allow USB clients to make direct calls to the hub driver without allocating IRPs. 


## -struct-fields




### -field Size

Specifies the size in bytes of the buffer that holds the interface pointers. 


### -field Version

Indicates, on input, the version of the interface. This member should have one of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
USB_BUSIF_USBDI_VERSION_0

</td>
<td>
Version 0 of the interface.

</td>
</tr>
<tr>
<td>
USB_BUSIF_USBDI_VERSION_1

</td>
<td>
Version 1 of the interface.

</td>
</tr>
<tr>
<td>
USB_BUSIF_USBDI_VERSION_2

</td>
<td>
Version 2 of the interface.

</td>
</tr>
<tr>
<td>
USB_BUSIF_USBDI_VERSION_3

</td>
<td>
Version 3 of the interface.

</td>
</tr>
</table>
 


### -field BusContext

Contains information that describes the USB bus and the USB bus driver that exposes this interface. This is an opaque entity that the caller must pass to the interface routines. 


### -field InterfaceReference

Pointer to a routine that increments the number of references to this interface. For more information about this routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_reference">InterfaceReference</a>. 


### -field InterfaceDereference

Pointer to a routine that decrements the number of references to this interface. For more information about this routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_dereference">InterfaceDereference</a>. 


### -field GetUSBDIVersion

Pointer to a routine that returns the USB interface version number, the version number of USB specification that defines the interface, along with host controller capabilities information. This routine returns the highest USBDI interface version that is supported by the port driver. For more information about this routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbbusif/nc-usbbusif-pusb_busiffn_getusbdi_version">GetUSBDIVersion</a>. 


### -field QueryBusTime

Pointer to a routine that returns the current 32-bit USB frame number. This routine replaces the <b>USBD_QueryBusTime</b> function provided by usbd.sys. For more information about this routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbbusif/nc-usbbusif-pusb_busiffn_query_bus_time">QueryBusTime</a>.


### -field SubmitIsoOutUrb

Reserved. Do not use.


### -field QueryBusInformation

Pointer to a routine that returns information about the bus. The information that is returned depends on the value of the <b>Level </b>member. If <b>Level</b> is 0, this routine returns bus bandwidth information. If <b>Level</b> is 1, it returns bus bandwidth information and the host controller's symbolic name. This routine replaces the <b>USBD_QueryBusInformation</b> function provided by usbd.sys. For more information about this routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbbusif/nc-usbbusif-pusb_busiffn_query_bus_information">QueryBusInformation</a>. 


## -remarks



For information about how to query for these interfaces, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Querying for USB Interfaces</a>. Callers of the routines in this structure can be running at IRQL <= DISPATCH_LEVEL. 




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff540046(v=vs.85)">Bus Driver Interface Routines for USB Client Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">USB Structures</a>
 

 

