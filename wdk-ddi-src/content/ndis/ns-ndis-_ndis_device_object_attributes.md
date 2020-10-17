---
UID: NS:ndis._NDIS_DEVICE_OBJECT_ATTRIBUTES
title: _NDIS_DEVICE_OBJECT_ATTRIBUTES (ndis.h)
description: The NDIS_DEVICE_OBJECT_ATTRIBUTES structure defines the attributes of a device that an NDIS filter or miniport driver can pass to the NdisRegisterDeviceEx function.
old-location: netvista\ndis_device_object_attributes.htm
tech.root: netvista
ms.assetid: 658e1597-eacf-4e9e-9f10-37f7646d38ad
ms.date: 05/02/2018
keywords: ["NDIS_DEVICE_OBJECT_ATTRIBUTES structure"]
ms.keywords: "*PNDIS_DEVICE_OBJECT_ATTRIBUTES, NDIS_DEVICE_OBJECT_ATTRIBUTES, NDIS_DEVICE_OBJECT_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], PNDIS_DEVICE_OBJECT_ATTRIBUTES, PNDIS_DEVICE_OBJECT_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], _NDIS_DEVICE_OBJECT_ATTRIBUTES, ndis/NDIS_DEVICE_OBJECT_ATTRIBUTES, ndis/PNDIS_DEVICE_OBJECT_ATTRIBUTES, ndis_devices_ref_85d7040d-1d34-42e4-ab6b-ef03ed95eeb9.xml, netvista.ndis_device_object_attributes"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.typenames: NDIS_DEVICE_OBJECT_ATTRIBUTES, *PNDIS_DEVICE_OBJECT_ATTRIBUTES
f1_keywords:
 - _NDIS_DEVICE_OBJECT_ATTRIBUTES
 - ndis/_NDIS_DEVICE_OBJECT_ATTRIBUTES
 - PNDIS_DEVICE_OBJECT_ATTRIBUTES
 - ndis/PNDIS_DEVICE_OBJECT_ATTRIBUTES
 - NDIS_DEVICE_OBJECT_ATTRIBUTES
 - ndis/NDIS_DEVICE_OBJECT_ATTRIBUTES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NDIS_DEVICE_OBJECT_ATTRIBUTES
---

# _NDIS_DEVICE_OBJECT_ATTRIBUTES structure


## -description

The NDIS_DEVICE_OBJECT_ATTRIBUTES structure defines the attributes of a device that an NDIS filter or
  miniport driver can pass to the 
  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterdeviceex">NdisRegisterDeviceEx</a> function.

## -struct-fields

### -field Header

The 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_DEVICE_OBJECT_ATTRIBUTES structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEVICE_OBJECT_ATTRIBUTES, the 
     <b>Revision</b> member to NDIS_DEVICE_OBJECT_ATTRIBUTES_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_DEVICE_OBJECT_ATTRIBUTES_REVISION_1.

### -field DeviceName

A pointer to a variable of type NDIS_STRING that contains a null-terminated Unicode string that
     names the device object. The string must be a full path name--for example, 
     \Device\\<i>DeviceName</i>. For Microsoft Windows 2000 and later, NDIS defines the NDIS_STRING type as a 
     <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> type.

### -field SymbolicName

A pointer to a variable of type NDIS_STRING that contains a Unicode string that is the
     Win32-visible name of the device being registered. Typically, 
     <b>SymbolicName</b> has the following format: 
     \DosDevices\\<i>SymbolicName</i>.

### -field MajorFunctions

A pointer to an array of one or more entry points for the device driver's dispatch routines. A
     driver must set the same number of separate dispatch entry points as the number of IRP_MJ_<i>XXX</i> codes that the driver handles for the device object. Each dispatch routine is declared as
     follows:
     


```
NTSTATUS
  (*PDRIVER_DISPATCH) (
    IN PDEVICE_OBJECT  DeviceObject,
    IN PIRP  Irp
);
```

The dispatch routine has the following parameters:





#### DeviceObject

The device object for the dispatch routine.



#### Irp

The IRP for the dispatch routine.

A driver must not supply entry points for PnP or Power Management handlers, because the created
     device object is not for a physical device and therefore does not receive PnP or Power Management
     IRPs.

### -field ExtensionSize

The driver-determined number of bytes to be allocated for the device extension of the device
     object. The internal structure of the device extension is driver-defined.

### -field DefaultSDDLString

A string representation for the default security settings of the device object. The security that
     is applied to the device object is derived from this string. 
     

The security setting is specified in a subset of Security Descriptor Definition Language (SDDL). A
     set of predefined constants (SDDL_DEVOBJ_<i>XXX</i>) is also provided. For more information, see 
     <a href="/windows-hardware/drivers/kernel/securing-device-objects">Securing Device Objects</a>.

### -field DeviceClassGuid

Reserved for NDIS. Set this member to <b>NULL</b>.

## -remarks

An NDIS filter or miniport driver can call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterdeviceex">NdisRegisterDeviceEx</a> function to
    register a device. To specify the device attributes, the driver allocates and initializes an
    NDIS_DEVICE_OBJECT_ATTRIBUTES structure and passes the structure to the 
    <i>DeviceObjectAttributes</i> parameter of 
    <b>NdisRegisterDeviceEx</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterdeviceex">NdisRegisterDeviceEx</a>



<a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>