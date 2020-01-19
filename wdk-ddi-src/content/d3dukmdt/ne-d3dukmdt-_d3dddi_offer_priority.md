---
UID: NE:d3dukmdt._D3DDDI_OFFER_PRIORITY
title: _D3DDDI_OFFER_PRIORITY (d3dukmdt.h)
description: Indicates the importance of video memory resources that the user-mode display driver offers for reuse.
old-location: display\d3dddi_offer_priority.htm
tech.root: display
ms.assetid: 2e43f782-c89c-4926-83db-efe737544065
ms.date: 05/10/2018
ms.keywords: D3DDDI_OFFER_PRIORITY, D3DDDI_OFFER_PRIORITY enumeration [Display Devices], D3DDDI_OFFER_PRIORITY_AUTO, D3DDDI_OFFER_PRIORITY_HIGH, D3DDDI_OFFER_PRIORITY_LOW, D3DDDI_OFFER_PRIORITY_NONE, D3DDDI_OFFER_PRIORITY_NORMAL, _D3DDDI_OFFER_PRIORITY, d3dukmdt/D3DDDI_OFFER_PRIORITY, d3dukmdt/D3DDDI_OFFER_PRIORITY_AUTO, d3dukmdt/D3DDDI_OFFER_PRIORITY_HIGH, d3dukmdt/D3DDDI_OFFER_PRIORITY_LOW, d3dukmdt/D3DDDI_OFFER_PRIORITY_NONE, d3dukmdt/D3DDDI_OFFER_PRIORITY_NORMAL, display.d3dddi_offer_priority
ms.topic: enum
f1_keywords:
 - "d3dukmdt/D3DDDI_OFFER_PRIORITY"
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- D3dukmdt.h
api_name:
- D3DDDI_OFFER_PRIORITY
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_OFFER_PRIORITY
---

# _D3DDDI_OFFER_PRIORITY enumeration


## -description


Indicates the importance of video memory resources  that the user-mode display driver offers for reuse.


## -enum-fields




### -field D3DDDI_OFFER_PRIORITY_NONE

The allocation should not be offered.

<div class="alert"><b>Note</b>  Do not use this value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_offerallocations">D3DDDICB_OFFERALLOCATIONS</a>.<b>Priority</b> member.</div>
<div> </div>

### -field D3DDDI_OFFER_PRIORITY_LOW

The allocation has low value and should be discarded before other offered allocations. Specify this type for allocations that have no useful content.


### -field D3DDDI_OFFER_PRIORITY_NORMAL

The allocation has useful content but can easily be regenerated.


### -field D3DDDI_OFFER_PRIORITY_HIGH

The allocation has useful content and cannot easily be regenerated. The video memory manager (which is part of Dxgkrnl.sys) should therefore avoid discarding this allocation before other offered allocations.


### -field D3DDDI_OFFER_PRIORITY_AUTO

The video memory manager should make a policy decision on the allocation's value based on its  priority for eviction.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_offerallocations">D3DDDICB_OFFERALLOCATIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_allocationlist">D3DDDI_ALLOCATIONLIST</a>
 

 

