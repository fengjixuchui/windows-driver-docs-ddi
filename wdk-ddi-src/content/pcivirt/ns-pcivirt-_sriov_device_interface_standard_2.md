---
UID: NS:pcivirt._SRIOV_DEVICE_INTERFACE_STANDARD_2
title: _SRIOV_DEVICE_INTERFACE_STANDARD_2 (pcivirt.h)
description: Stores function pointers to callback functions implemented by the physical function (PF) driver in the device stack for the of the SR-IOV device. This is an extended version of SRIOV_DEVICE_INTERFACE_STANDARD.
old-location: pci\sriov_device_interface_standard_2.htm
tech.root: PCI
ms.assetid: 46c9fa94-283c-481e-9fb1-2ed63df00386
ms.date: 02/24/2018
ms.keywords: "*PSRIOV_DEVICE_INTERFACE_STANDARD_2, PCI.sriov_device_interface_standard_2, SRIOV_DEVICE_INTERFACE_STANDARD_2, SRIOV_DEVICE_INTERFACE_STANDARD_2 structure [Buses], _SRIOV_DEVICE_INTERFACE_STANDARD_2, pcivirt/SRIOV_DEVICE_INTERFACE_STANDARD_2"
ms.topic: struct
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
- SRIOV_DEVICE_INTERFACE_STANDARD_2
product:
- Windows
targetos: Windows
req.typenames: SRIOV_DEVICE_INTERFACE_STANDARD_2, *PSRIOV_DEVICE_INTERFACE_STANDARD_2
---

# _SRIOV_DEVICE_INTERFACE_STANDARD_2 structure


## -description


Stores function pointers to callback functions implemented by the physical function (PF) driver  in the device stack for the of the SR-IOV device. This is an extended version of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pcivirt/ns-pcivirt-_sriov_device_interface_standard">SRIOV_DEVICE_INTERFACE_STANDARD</a>.


## -syntax


```cpp
typedef struct _SRIOV_DEVICE_INTERFACE_STANDARD_2 {
  USHORT                           Size;
  USHORT                           Version;
  PVOID                            Context;
  PINTERFACE_REFERENCE             InterfaceReference;
  PINTERFACE_REFERENCE             InterfaceDereference;
  PSRIOV_READ_CONFIG               ReadVfConfig;
  PSRIOV_WRITE_CONFIG              WriteVfConfig;
  PSRIOV_READ_BLOCK                ReadVfConfigBlock;
  PSRIOV_WRITE_BLOCK               WriteVfConfigBlock;
  PSRIOV_QUERY_PROBED_BARS         QueryProbedBars;
  PSRIOV_GET_VENDOR_AND_DEVICE_IDS GetVendorAndDevice;
  PSRIOV_GET_DEVICE_LOCATION       GetDeviceLocation;
  PSRIOV_RESET_FUNCTION            ResetVf;
  PSRIOV_SET_POWER_STATE           SetVfPowerState;
  PSRIOV_GET_RESOURCE_FOR_BAR      GetResourceForBar;
  PSRIOV_QUERY_LUID                QueryLuid;
  PSRIOV_QUERY_PROBED_BARS_2       QueryProbedBars_2;
  PSRIOV_QUERY_VF_LUID             QueryVfLuid;
  PSRIOV_QUERY_LUID_VF             QueryLuidVf;
} SRIOV_DEVICE_INTERFACE_STANDARD_2, SRIOV_DEVICE_INTERFACE_STANDARD_2;
```


## -struct-fields




### -field Size

Size of this structure.


### -field Version

Version of this structure


### -field Context

Driver-defined context passed by the driver.


### -field InterfaceReference

Pointer to a routine that increments the number of references to this interface. For more information about this routine, see <a href="..\wudfwdm\nc-wudfwdm-pinterface_reference.md">InterfaceReference</a>.


### -field InterfaceDereference

Pointer to a routine that decrements the number of references to this interface. For more information about this routine, see <a href="..\wudfwdm\nc-wudfwdm-pinterface_dereference.md">InterfaceDereference</a>.


### -field ReadVfConfig

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pcivirt/nc-pcivirt-sriov_read_config">SRIOV_READ_CONFIG</a> callback function that serves as a handler for reading the VF’s configurations space from the non-privileged VM.


### -field WriteVfConfig

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pcivirt/nc-pcivirt-sriov_write_config">SRIOV_WRITE_CONFIG</a> callback function that serves as a handler for writing the VF’s configuration space from the non-privileged VM.


### -field ReadVfConfigBlock

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pcivirt/nc-pcivirt-sriov_read_block">SRIOV_READ_BLOCK</a> callback function that serves as a handler for reading blocks of configuration data from the non-privileged VM.


### -field WriteVfConfigBlock

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pcivirt/nc-pcivirt-sriov_write_block">SRIOV_WRITE_BLOCK</a> callback function that serves as a handler for writing blocks of configuration data from the non-privileged VM..


### -field QueryProbedBars

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pcivirt/nc-pcivirt-sriov_query_probed_bars">SRIOV_QUERY_PROBED_BARS</a> callback function that allows a non-privileged VM to determine the value of the VF’s Base Address Registers if the value of -1 previously is written.


### -field GetVendorAndDevice

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pcivirt/nc-pcivirt-sriov_get_vendor_and_device_ids">SRIOV_GET_VENDOR_AND_DEVICE_IDS</a> callback function that supplies the values from which the Plug and Play IDs for device is derived.


### -field GetDeviceLocation

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pcivirt/nc-pcivirt-sriov_get_device_location">SRIOV_GET_DEVICE_LOCATION</a> callback function that allows the a non-privileged VM to determine the bus to which the device is attached.


### -field ResetVf

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pcivirt/nc-pcivirt-sriov_reset_function">SRIOV_RESET_FUNCTION</a> callback function that causes the VF to be reset.


### -field SetVfPowerState

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pcivirt/nc-pcivirt-sriov_set_power_state">SRIOV_SET_POWER_STATE</a> callback function that serves as a handle for changing the device’s power state from the non-privileged VM.


### -field GetResourceForBar

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pcivirt/nc-pcivirt-sriov_get_resource_for_bar">SRIOV_GET_RESOURCE_FOR_BAR</a> callback function that gets the translated resource for a specific BAR.


### -field QueryLuid

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pcivirt/nc-pcivirt-sriov_query_luid">SRIOV_QUERY_LUID</a> callback function that gets the unique identifier of the VF.


### -field QueryProbedBars_2

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pcivirt/nc-pcivirt-sriov_query_probed_bars_2">SRIOV_QUERY_PROBED_BARS_2</a> callback function.


### -field QueryVfLuid

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pcivirt/nc-pcivirt-sriov_query_vf_luid">SRIOV_QUERY_VF_LUID</a> callback function that gets the unique identifier of the VF.


### -field QueryLuidVf

Pointer to the driver's implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pcivirt/nc-pcivirt-sriov_query_luid_vf">SRIOV_QUERY_LUID_VF</a> callback function that gets VF index for the specified unique identifier.

