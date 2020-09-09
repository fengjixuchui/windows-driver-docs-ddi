---
UID: NS:wdm._DEVICE_RESET_INTERFACE_STANDARD
title: _DEVICE_RESET_INTERFACE_STANDARD (wdm.h)
description: The DEVICE_RESET_INTERFACE_STANDARD structure enables function drivers to reset and recover malfunctioning devices. This structure describes the GUID_DEVICE_RESET_INTERFACE_STANDARD interface.
old-location: kernel\device_reset_interface_standard.htm
tech.root: kernel
ms.assetid: DD8A7E50-664B-49B8-905B-A5BE02A48DCE
ms.date: 11/15/2018
keywords: ["DEVICE_RESET_INTERFACE_STANDARD structure"]
ms.keywords: "*PDEVICE_RESET_INTERFACE_STANDARD, DEVICE_RESET_INTERFACE_STANDARD, DEVICE_RESET_INTERFACE_STANDARD structure [Kernel-Mode Driver Architecture], PDEVICE_RESET_INTERFACE_STANDARD, PDEVICE_RESET_INTERFACE_STANDARD structure pointer [Kernel-Mode Driver Architecture], _DEVICE_RESET_INTERFACE_STANDARD, kernel.device_reset_interface_standard, wdm/DEVICE_RESET_INTERFACE_STANDARD, wdm/PDEVICE_RESET_INTERFACE_STANDARD"
req.header: wdm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.typenames: DEVICE_RESET_INTERFACE_STANDARD, *PDEVICE_RESET_INTERFACE_STANDARD
f1_keywords:
 - _DEVICE_RESET_INTERFACE_STANDARD
 - wdm/_DEVICE_RESET_INTERFACE_STANDARD
 - PDEVICE_RESET_INTERFACE_STANDARD
 - wdm/PDEVICE_RESET_INTERFACE_STANDARD
 - DEVICE_RESET_INTERFACE_STANDARD
 - wdm/DEVICE_RESET_INTERFACE_STANDARD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - DEVICE_RESET_INTERFACE_STANDARD
---

# _DEVICE_RESET_INTERFACE_STANDARD structure


## -description

The <b>DEVICE_RESET_INTERFACE_STANDARD</b> structure enables function drivers to reset and recover malfunctioning devices. This structure describes the GUID_DEVICE_RESET_INTERFACE_STANDARD 
interface. For more information see [Working with the GUID_DEVICE_RESET_INTERFACE_STANDARD](https://docs.microsoft.com/windows-hardware/drivers/kernel/working-with-guid-device-reset-interface-standard).

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Version

The driver-defined interface version.

### -field Context

A pointer to interface-specific context information

### -field InterfaceReference

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_reference">InterfaceReference</a> routine that increments the interface's reference count.

### -field InterfaceDereference

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_dereference">InterfaceDereference</a> routine that decrements the interface's reference count.

### -field DeviceReset

A pointer to the interface's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pdevice_reset_handler">DeviceReset</a> routine. This routine can be used by function drivers to attempt to reset and recover a malfunctioning device.

### -field SupportedResetTypes

### -field Reserved

This member is reserved for future use.

## -remarks

The <b>DEVICE_RESET_INTERFACE_STANDARD</b> structure is an extension of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a> structure. A driver obtains a pointer to the <b>DEVICE_RESET_INTERFACE_STANDARD</b> structure by sending an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-interface">IRP_MN_QUERY_INTERFACE</a> IRP to its bus driver with <b>InterfaceType</b> set to GUID_DEVICE_RESET_INTERFACE_STANDARD.

For more information about the purpose of this interface, see [Working with the GUID_DEVICE_RESET_INTERFACE_STANDARD](https://docs.microsoft.com/windows-hardware/drivers/kernel/working-with-guid-device-reset-interface-standard).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pdevice_reset_handler">DeviceReset</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-interface">IRP_MN_QUERY_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_dereference">InterfaceDereference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_reference">InterfaceReference</a>

