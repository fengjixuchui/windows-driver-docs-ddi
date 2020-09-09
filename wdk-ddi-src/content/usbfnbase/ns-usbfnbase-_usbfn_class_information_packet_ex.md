---
UID: NS:usbfnbase._USBFN_CLASS_INFORMATION_PACKET_EX
title: _USBFN_CLASS_INFORMATION_PACKET_EX (usbfnbase.h)
description: Describes device interface class information associated with a USB interface. This structure can be used to describe single and multi-interface functions.
old-location: buses\usbfn_class_information_packet_ex.htm
tech.root: usbref
ms.assetid: 373D7CA9-AF1B-46E8-AE6A-F693A9214527
ms.date: 05/07/2018
keywords: ["USBFN_CLASS_INFORMATION_PACKET_EX structure"]
ms.keywords: "*PUSBFN_CLASS_INFORMATION_PACKET_EX, PUSBFN_CLASS_INFORMATION_PACKET_EX, PUSBFN_CLASS_INFORMATION_PACKET_EX structure pointer [Buses], USBFN_CLASS_INFORMATION_PACKET_EX, USBFN_CLASS_INFORMATION_PACKET_EX structure [Buses], _USBFN_CLASS_INFORMATION_PACKET_EX, buses.usbfn_class_information_packet_ex, usbfnbase/PUSBFN_CLASS_INFORMATION_PACKET_EX, usbfnbase/USBFN_CLASS_INFORMATION_PACKET_EX"
req.header: usbfnbase.h
req.include-header: 
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
req.typenames: USBFN_CLASS_INFORMATION_PACKET_EX, *PUSBFN_CLASS_INFORMATION_PACKET_EX
f1_keywords:
 - _USBFN_CLASS_INFORMATION_PACKET_EX
 - usbfnbase/_USBFN_CLASS_INFORMATION_PACKET_EX
 - PUSBFN_CLASS_INFORMATION_PACKET_EX
 - usbfnbase/PUSBFN_CLASS_INFORMATION_PACKET_EX
 - USBFN_CLASS_INFORMATION_PACKET_EX
 - usbfnbase/USBFN_CLASS_INFORMATION_PACKET_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbfnbase.h
api_name:
 - USBFN_CLASS_INFORMATION_PACKET_EX
---

# _USBFN_CLASS_INFORMATION_PACKET_EX structure


## -description

Describes device interface class information associated with a USB interface. This structure can be used to describe single and multi-interface functions.

## -struct-fields

### -field FullSpeedClassInterfaceEx

### -field HighSpeedClassInterfaceEx

### -field SuperSpeedClassInterfaceEx

### -field InterfaceName

### -field InterfaceGuid

### -field HasInterfaceGuid

Determines whether the driver has published a device interface is GUID. 


#### - FullSpeedClassInterface

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnbase/ns-usbfnbase-_usbfn_class_interface_ex">USBFN_CLASS_INTERFACE_EX</a> structure that describes an interface for full speed device.


#### - HighSpeedClassInterface

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnbase/ns-usbfnbase-_usbfn_class_interface_ex">USBFN_CLASS_INTERFACE_EX</a> structure that describes an interface for high speed device.


#### - InterfaceGuid[MAX_INTERFACE_GUID_LENGTH]

A string from which the driver can derive the device interface GUID.


#### - InterfaceName[MAX_INTERFACE_NAME_LENGTH]

A string that contains the interface name.


#### - SuperSpeedClassInterface

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnbase/ns-usbfnbase-_usbfn_class_interface">USBFN_CLASS_INTERFACE</a> structure that describes an interface for SuperSpeed device.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnbase/ns-usbfnbase-_usbfn_class_interface">USBFN_CLASS_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreatesymboliclink">WdfDeviceCreateSymbolicLink</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicesetdeviceinterfacestate">WdfDeviceSetDeviceInterfaceState</a>

