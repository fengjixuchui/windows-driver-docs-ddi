---
UID: NS:pepfx._PEP_CRASHDUMP_INFORMATION
title: _PEP_CRASHDUMP_INFORMATION (pepfx.h)
description: The PEP_CRASHDUMP_INFORMATION structure contains information about a crash-dump device.
old-location: kernel\pep_crashdump_information.htm
tech.root: kernel
ms.assetid: B1F680CB-8F82-4B31-A62E-23804FEB0107
ms.date: 04/30/2018
ms.keywords: "*PPEP_CRASHDUMP_INFORMATION, PEP_CRASHDUMP_INFORMATION, PEP_CRASHDUMP_INFORMATION structure [Kernel-Mode Driver Architecture], PPEP_CRASHDUMP_INFORMATION, PPEP_CRASHDUMP_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _PEP_CRASHDUMP_INFORMATION, kernel.pep_crashdump_information, pepfx/PEP_CRASHDUMP_INFORMATION, pepfx/PPEP_CRASHDUMP_INFORMATION"
ms.topic: struct
f1_keywords:
 - "pepfx/PEP_CRASHDUMP_INFORMATION"
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
- PEP_CRASHDUMP_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: PEP_CRASHDUMP_INFORMATION, *PPEP_CRASHDUMP_INFORMATION
---

# _PEP_CRASHDUMP_INFORMATION structure


## -description


The <b>PEP_CRASHDUMP_INFORMATION</b> structure contains information about a crash-dump device.


## -struct-fields




### -field DeviceHandle

[in] A PEPHANDLE value that identifies the crash-dump device. The platform extension plug-in (PEP) supplied this handle in response to a previous <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a> notification.


### -field DeviceContext

[in] A pointer to a device-specific context. This pointer is the <i>Context</i> parameter value that the device driver previously passed to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxpoweroncrashdumpdevice">PoFxPowerOnCrashdumpDevice</a> routine. The context contains information in a format that is defined by the device driver and is understood by the PEP. The context is opaque to the operating system. This member value can be NULL if the PEP does not require a context.


## -remarks



The <i>CrashdumpInformation</i> parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pepcallbackpoweroncrashdumpdevice">PowerOnDumpDeviceCallback</a> routine is a pointer to a <b>PEP_CRASHDUMP_INFORMATION</b> structure.

When a fatal system error occurs, the devices in the crash-dump device chain (storage controller, PCI controller, and so on) need to be turned on so that the Windows kernel can write a crash-dump file to disk.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxpoweroncrashdumpdevice">PoFxPowerOnCrashdumpDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pepcallbackpoweroncrashdumpdevice">PowerOnDumpDeviceCallback</a>
 

 

