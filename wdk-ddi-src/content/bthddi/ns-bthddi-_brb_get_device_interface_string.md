---
UID: NS:bthddi._BRB_GET_DEVICE_INTERFACE_STRING
title: _BRB_GET_DEVICE_INTERFACE_STRING (bthddi.h)
description: The _BRB_GET_DEVICE_INTERFACE_STRING structure describes the device interface string for the current device object.
old-location: bltooth\_brb_get_device_interface_string.htm
tech.root: bltooth
ms.assetid: 340e4b9a-9959-4eda-b26b-674f7fca7156
ms.date: 04/27/2018
ms.keywords: "_BRB_GET_DEVICE_INTERFACE_STRING, _BRB_GET_DEVICE_INTERFACE_STRING structure [Bluetooth Devices], bltooth._brb_get_device_interface_string, bth_structs_3d85c9ac-2714-4d6c-8a3e-f8908d8e5be9.xml, bthddi/_BRB_GET_DEVICE_INTERFACE_STRING"
ms.topic: struct
f1_keywords:
 - "bthddi/_BRB_GET_DEVICE_INTERFACE_STRING"
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
- bthddi.h
api_name:
- _BRB_GET_DEVICE_INTERFACE_STRING
product:
- Windows
targetos: Windows
req.typenames: 
---

# _BRB_GET_DEVICE_INTERFACE_STRING structure


## -description


The _BRB_GET_DEVICE_INTERFACE_STRING structure describes the device interface string for the current
  device object.


## -struct-fields




### -field Hdr

A 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field DeviceInterfaceString

A pointer to the buffer to contain the device interface string.


### -field DeviceInterfaceStringCbLength

On input, this member specifies the length, in bytes, of the device interface string. On output,
     this member specifies the number of bytes required for the string if the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_get_device_interface_string">
     BRB_GET_DEVICE_INTERFACE_STRING</a> BRB fails and returns STATUS_MORE_ENTRIES because of insufficient
     buffer length. If the BRB call succeeds, this member contains the number of bytes copied.


## -remarks



To get the device interface string for the current device object, profile drivers should 
    <a href="https://docs.microsoft.com/previous-versions/ff536657(v=vs.85)">build and send</a> a 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_get_device_interface_string">
    BRB_GET_DEVICE_INTERFACE_STRING</a> request.

The Bluetooth driver stack performs an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioregisterdeviceinterface">IoRegisterDeviceInterface</a> call on
    each device object it creates. The BRB returns the device interface string returned by that call. This
    can be useful for registering for events.

If the buffer pointed to by the 
    <b>DeviceInterfaceString</b> member is not large enough to hold the string, the call fails and the 
    <b>DeviceInterfaceStringCbLength</b> member contains the required buffer length.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_get_device_interface_string">
   BRB_GET_DEVICE_INTERFACE_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioregisterdeviceinterface">IoRegisterDeviceInterface</a>
 

 

