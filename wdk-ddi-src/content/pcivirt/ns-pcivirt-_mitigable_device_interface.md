---
UID: NS:pcivirt._MITIGABLE_DEVICE_INTERFACE
title: _MITIGABLE_DEVICE_INTERFACE (pcivirt.h)
description: Stores function pointers to callback functions implemented by the physical function (PF) driver for the mitigable device interface.
old-location: pci\mitigable_device_interface.htm
tech.root: PCI
ms.assetid: 1fac7c03-2a48-4b29-951d-c777fbec7dd3
ms.date: 02/24/2018
keywords: ["_MITIGABLE_DEVICE_INTERFACE structure"]
ms.keywords: "*PMITIGABLE_DEVICE_INTERFACE, MITIGABLE_DEVICE_INTERFACE, MITIGABLE_DEVICE_INTERFACE structure [Buses], PCI.mitigable_device_interface, _MITIGABLE_DEVICE_INTERFACE, pcivirt/MITIGABLE_DEVICE_INTERFACE"
f1_keywords:
 - "pcivirt/MITIGABLE_DEVICE_INTERFACE"
req.header: pcivirt.h
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Pcivirt.h
api_name:
- MITIGABLE_DEVICE_INTERFACE
product:
- Windows
targetos: Windows
req.typenames: MITIGABLE_DEVICE_INTERFACE, *PMITIGABLE_DEVICE_INTERFACE
---

# _MITIGABLE_DEVICE_INTERFACE structure


## -description


Stores function pointers to callback functions implemented by the physical function (PF) driver  for the mitigable device interface.


## -syntax


```cpp
typedef struct _MITIGABLE_DEVICE_INTERFACE {
  USHORT                         Size;
  USHORT                         Version;
  PVOID                          Context;
  PINTERFACE_REFERENCE           InterfaceReference;
  PINTERFACE_REFERENCE           InterfaceDereference;
  PREAD_WRITE_MITIGATED_REGISTER ReadWriteMitigatedRegister;
} MITIGABLE_DEVICE_INTERFACE, MITIGABLE_DEVICE_INTERFACE;
```


## -struct-fields




### -field Size

Size of this structure.


### -field Version

Version of this structure


### -field Context

Driver-defined context passed by the driver.


### -field InterfaceReference

Pointer to a routine that increments the number of references to this interface. For more information about this routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_reference">InterfaceReference</a>.


### -field InterfaceDereference

Pointer to a routine that decrements the number of references to this interface. For more information about this routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_dereference">InterfaceDereference</a>.


### -field ReadWriteMitigatedRegister

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/nc-pcivirt-read_write_mitigated_register">READ_WRITE_MITIGATED_REGISTER</a> callback function.


## -remarks

This callback function is implemented by the physical function (PF) driver. This function reads and writes mitigated address spaces, in the form required by GUID_MITIGABLE_DEVICE_INTERFACE.

The PF driver registers its implementation by setting the <b>ReadVfConfig</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/ns-pcivirt-_sriov_device_interface_standard">SRIOV_DEVICE_INTERFACE_STANDARD</a>, configuring a <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.



