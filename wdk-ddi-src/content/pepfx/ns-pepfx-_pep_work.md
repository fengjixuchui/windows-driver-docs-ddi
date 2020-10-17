---
UID: NS:pepfx._PEP_WORK
title: _PEP_WORK (pepfx.h)
description: The PEP_WORK structure indicates whether the PEP has a work request to submit to the Windows power management framework (PoFx).
old-location: kernel\pep_work.htm
tech.root: kernel
ms.assetid: 7C6ACFDD-809E-4E75-8E4D-8A4E0207593E
ms.date: 04/30/2018
keywords: ["PEP_WORK structure"]
ms.keywords: "*PPEP_WORK, PEP_WORK, PEP_WORK structure [Kernel-Mode Driver Architecture], PPEP_WORK, PPEP_WORK structure pointer [Kernel-Mode Driver Architecture], _PEP_WORK, kernel.pep_work, pepfx/PEP_WORK, pepfx/PPEP_WORK"
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
targetos: Windows
req.typenames: PEP_WORK, *PPEP_WORK
f1_keywords:
 - _PEP_WORK
 - pepfx/_PEP_WORK
 - PPEP_WORK
 - pepfx/PPEP_WORK
 - PEP_WORK
 - pepfx/PEP_WORK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_WORK
---

# _PEP_WORK structure (pepfx.h)


## -description

The <b>PEP_WORK</b> structure indicates whether the PEP has a work request to submit to the Windows <a href="/windows-hardware/drivers/kernel/overview-of-the-power-management-framework">power management framework</a> (PoFx).

## -struct-fields

### -field WorkInformation

[out] A pointer to a PEP-allocated <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_information">PEP_WORK_INFORMATION</a> structure that describes the work that the PEP is requesting. If <b>NeedWork</b> is TRUE, <b>WorkInformation</b> must point to a valid <b>PEP_WORK_INFORMATION</b> structure. If <b>NeedWork</b> is FALSE, <b>WorkInformation</b> must be NULL.

### -field NeedWork

[out] Whether the PEP has a work request to submit. Set this member to TRUE if the PEP has a work request, or to FALSE if the PEP has no work to request.

## -remarks

This structure is used by the <a href="/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_WORK</a> notification. Both members of the structure contain values that the PEP writes to the structure in response to this notification.

## -see-also

<a href="/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_WORK</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_information">PEP_WORK_INFORMATION</a>