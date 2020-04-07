---
UID: NS:pepfx._PEP_ACPI_UNREGISTER_DEVICE
title: _PEP_ACPI_UNREGISTER_DEVICE (pepfx.h)
description: The PEP_ACPI_UNREGISTER_DEVICE structure contains information about a device that has been unregistered from ACPI services.
old-location: kernel\pep_acpi_unregister_device.htm
tech.root: kernel
ms.assetid: AA9D9AB3-B799-4D21-A418-D29360BBE605
ms.date: 04/30/2018
keywords: ["_PEP_ACPI_UNREGISTER_DEVICE structure"]
ms.keywords: "*PPEP_ACPI_UNREGISTER_DEVICE, PEP_ACPI_UNREGISTER_DEVICE, PEP_ACPI_UNREGISTER_DEVICE structure [Kernel-Mode Driver Architecture], PPEP_ACPI_UNREGISTER_DEVICE, PPEP_ACPI_UNREGISTER_DEVICE structure pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_UNREGISTER_DEVICE, kernel.pep_acpi_unregister_device, pepfx/PEP_ACPI_UNREGISTER_DEVICE, pepfx/PPEP_ACPI_UNREGISTER_DEVICE"
f1_keywords:
 - "pepfx/PEP_ACPI_UNREGISTER_DEVICE"
req.header: pepfx.h
req.include-header: Pep_x.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pepfx.h
api_name:
- PEP_ACPI_UNREGISTER_DEVICE
product:
- Windows
targetos: Windows
req.typenames: PEP_ACPI_UNREGISTER_DEVICE, *PPEP_ACPI_UNREGISTER_DEVICE
---

# _PEP_ACPI_UNREGISTER_DEVICE structure


## -description


The <b>PEP_ACPI_UNREGISTER_DEVICE</b> structure contains information about a device that has been unregistered from ACPI services.


## -struct-fields




### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device's registration for ACPI services. The platform extension plug-in (PEP) supplied this handle in response to a previous <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_register_device">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a> notification.


### -field InputFlags

[in] A set of input flags. No flags are currently defined for this member, which is always set to PEP_ACPI_UNREGISTER_DEVICE_INPUT_FLAG_NONE (0x0).


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_NOTIFY_ACPI_UNREGISTER_DEVICE</a> notification. The <b>DeviceHandle</b> and <b>InputFlags</b> members contain input values that are supplied by the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> when this notification is sent.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_register_device">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_NOTIFY_ACPI_UNREGISTER_DEVICE</a>
 

 

