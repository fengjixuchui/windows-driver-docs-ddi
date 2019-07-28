---
UID: NS:pep_x._PEP_COMPONENT_ACTIVE
title: _PEP_COMPONENT_ACTIVE (pep_x.h)
description: The PEP_COMPONENT_ACTIVE structure identifies a component that is making a transition between the idle condition and the active condition.
old-location: kernel\pep_component_active.htm
tech.root: kernel
ms.assetid: 58C2FFFC-2EAC-406B-943A-491AF3538F78
ms.date: 04/30/2018
ms.keywords: "*PPEP_COMPONENT_ACTIVE, PEP_COMPONENT_ACTIVE, PEP_COMPONENT_ACTIVE structure [Kernel-Mode Driver Architecture], PPEP_COMPONENT_ACTIVE, PPEP_COMPONENT_ACTIVE structure pointer [Kernel-Mode Driver Architecture], _PEP_COMPONENT_ACTIVE, kernel.pep_component_active, pep_x/PEP_COMPONENT_ACTIVE, pep_x/PPEP_COMPONENT_ACTIVE"
ms.topic: struct
f1_keywords:
 - "pep_x/PEP_COMPONENT_ACTIVE"
req.header: pep_x.h
req.include-header: Pepfx.h
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
- pep_x.h
api_name:
- PEP_COMPONENT_ACTIVE
product:
- Windows
targetos: Windows
req.typenames: PEP_COMPONENT_ACTIVE, *PPEP_COMPONENT_ACTIVE
---

# _PEP_COMPONENT_ACTIVE structure


## -description


The <b>PEP_COMPONENT_ACTIVE</b> structure identifies a component that is making a transition between the idle condition and the active condition.


## -struct-fields




### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device. The PEP supplied this handle in response to a previous <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a> notification.


### -field Component

[in] The index that identifies the component. This member is an index into the <b>Components</b> array in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_device_register_v2">PEP_DEVICE_REGISTER_V2</a> structure that the PEP previously supplied in response to the <b>PEP_DPM_REGISTER_DEVICE</b> notification for this device. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


### -field Active

[in] Whether the component is making a transition to the active condition. If TRUE, the component is making a transition from the idle condition to the active condition. If FALSE, the component is making a transition from the active condition to the idle condition.


### -field WorkInformation

[out] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_work_information">PEP_WORK_INFORMATION</a> structure that describes the work that the PEP requests in response to this notification. If <b>NeedWork</b> is TRUE, <b>WorkInformation</b> must point to a valid <b>PEP_WORK_INFORMATION</b> structure. If <b>NeedWork</b> is FALSE, <b>WorkInformation</b> must be NULL.


### -field NeedWork

[out] Whether the PEP has a work request to submit in response to this notification. Set to TRUE if the PEP has work to request, or to FALSE if the PEP has no work to request.


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pep_x/ns-pep_x-_pep_component_active">PEP_DPM_COMPONENT_ACTIVE</a> notification. The first three members of the structure contain input values that are supplied by the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">power management framework</a> (PoFx). The last two members contain output values that the PEP writes to the structure in response to this notification.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_device_register_v2">PEP_DEVICE_REGISTER_V2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pep_x/ns-pep_x-_pep_component_active">PEP_DPM_COMPONENT_ACTIVE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_work_information">PEP_WORK_INFORMATION</a>
 

 

