---
UID: NS:d3dukmdt.D3DDDI_EVICT_FLAGS
title: D3DDDI_EVICT_FLAGS (d3dukmdt.h)
description: D3DDDI_EVICT_FLAGS specifies the eviction behavior.
old-location: display\d3dddi_evict_flags.htm
tech.root: display
ms.assetid: 443671F1-98F5-4F9F-900B-37E3E50770CE
ms.date: 05/10/2018
keywords: ["D3DDDI_EVICT_FLAGS structure"]
ms.keywords: D3DDDI_EVICT_FLAGS, D3DDDI_EVICT_FLAGS structure [Display Devices], d3dukmdt/D3DDDI_EVICT_FLAGS, display.d3dddi_evict_flags
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
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
targetos: Windows
req.typenames: D3DDDI_EVICT_FLAGS
f1_keywords:
 - D3DDDI_EVICT_FLAGS
 - d3dukmdt/D3DDDI_EVICT_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - D3DDDI_EVICT_FLAGS
---

# D3DDDI_EVICT_FLAGS structure


## -description

<b>D3DDDI_EVICT_FLAGS</b> specifies the eviction behavior.

## -struct-fields

### -field EvictOnlyIfNecessary

When set, this indicates that the resource may be used again in the near future and instructs the OS to try to defer actual resource eviction from the GPU until low memory conditions. When not set, this instructs the OS that the resource will no longer be used and that the eviction should be performed at the earliest opportunity. 

<div class="alert"><b>Note</b>  This flag is ignored if the residency reference count does not hit zero because the allocation will not be evicted until that time.</div>
<div> </div>

### -field NotWrittenTo

When set, this indicates that the resource has not been written to by the GPU since the time it was made resident. This allows the OS to optimize the eviction process by discarding the allocation contents instead of paging it out to the system memory. The driver must opt-in to use this flag. By default, the value is zero and the allocation is considered dirty during eviction. Unlike <b>EvictOnlyIfNecessary</b>, the driver does not need to defer setting this flag until the last call to <b>Evict</b> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_evictcb">pfnEvictCb</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtevict">D3DKMTEvict</a>), and the effects of specifying this flag take place immediately. In other words, if the driver calls <b>MakeResident</b> multiple times, it is valid for any one of the subsequent <b>Evict</b> operations to specify this flag. The driver is not expected to track this flag until the last call.

### -field Reserved

This member is reserved and should be set to zero.

### -field Value

The consolidated value of the flags in the structure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtevict">D3DKMTEvict</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_evictcb">pfnEvictCb</a>

