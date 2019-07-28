---
UID: NE:d3dkmdt._DXGK_GENERAL_ERROR_CODE
title: _DXGK_GENERAL_ERROR_CODE (d3dkmdt.h)
description: The DXGK_GENERAL_ERROR_CODE enumeration specifies a set of predefined graphics processing unit (GPU) errors reported via a page fault interrupt.
old-location: display\dxgk_general_error_code.htm
tech.root: display
ms.assetid: 678998C5-DC3B-471D-ADBF-876EFB53D227
ms.date: 05/10/2018
ms.keywords: DXGK_GENERAL_ERROR_CODE, DXGK_GENERAL_ERROR_CODE enumeration [Display Devices], DXGK_GENERAL_ERROR_INVALID_INSTRUCTION, DXGK_GENERAL_ERROR_PAGE_FAULT, _DXGK_GENERAL_ERROR_CODE, d3dkmdt/DXGK_GENERAL_ERROR_CODE, d3dkmdt/DXGK_GENERAL_ERROR_INVALID_INSTRUCTION, d3dkmdt/DXGK_GENERAL_ERROR_PAGE_FAULT, display.dxgk_general_error_code
ms.topic: enum
f1_keywords:
 - "d3dkmdt/DXGK_GENERAL_ERROR_CODE"
req.header: d3dkmdt.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- D3dkmdt.h
api_name:
- DXGK_GENERAL_ERROR_CODE
product:
- Windows
targetos: Windows
req.typenames: DXGK_GENERAL_ERROR_CODE
---

# _DXGK_GENERAL_ERROR_CODE enumeration


## -description


The <b>DXGK_GENERAL_ERROR_CODE</b> enumeration specifies a set of predefined graphics processing unit (GPU) errors reported via a page fault interrupt.


## -enum-fields




### -field DXGK_GENERAL_ERROR_PAGE_FAULT

Indicates that the GPU encountered a page fault. The <b>FaultedVirtualAddress</b> and <b>PageTableLevel</b> members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkargcb_notify_interrupt_data">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a> structure should be used to provide further information about the GPU virtual address operation that caused the fault.


### -field DXGK_GENERAL_ERROR_INVALID_INSTRUCTION

Indicates that the GPU encountered an invalid instruction in the DMA command buffer.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkargcb_notify_interrupt_data">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a>
 

 

