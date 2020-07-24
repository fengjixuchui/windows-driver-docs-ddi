---
UID: NS:d3dumddi._D3DDDICB_CREATECONTEXT
title: _D3DDDICB_CREATECONTEXT (d3dumddi.h)
description: The D3DDDICB_CREATECONTEXT structure describes a context to create.
old-location: display\d3dddicb_createcontext.htm
tech.root: display
ms.assetid: 6bee57b5-f4b3-424c-aeb5-3bf65ab16392
ms.date: 05/10/2018
keywords: ["_D3DDDICB_CREATECONTEXT structure"]
ms.keywords: D3DDDICB_CREATECONTEXT, D3DDDICB_CREATECONTEXT structure [Display Devices], D3D_param_Structs_9ad6c5e1-c3aa-4546-b3c9-c07c8350093b.xml, _D3DDDICB_CREATECONTEXT, d3dumddi/D3DDDICB_CREATECONTEXT, display.d3dddicb_createcontext
f1_keywords:
 - "d3dumddi/D3DDDICB_CREATECONTEXT"
 - "D3DDDICB_CREATECONTEXT"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
- d3dumddi.h
api_name:
- D3DDDICB_CREATECONTEXT
targetos: Windows
req.typenames: D3DDDICB_CREATECONTEXT
---

# _D3DDDICB_CREATECONTEXT structure


## -description


The D3DDDICB_CREATECONTEXT structure describes a context to create.


## -struct-fields




### -field NodeOrdinal

[in] The zero-based index for the node that the context is scheduled on.


### -field EngineAffinity

[in] The zero-based index for the engine, within the node that <b>NodeOrdinal</b> specifies, that the context can run in.


### -field Flags

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_createcontextflags">D3DDDI_CREATECONTEXTFLAGS</a> structure that indicates, in bit-field flags, how to create the context. 


### -field pPrivateDriverData

[in] A pointer to private data that is passed to a display miniport driver. 


### -field PrivateDriverDataSize

[in] The size, in bytes, of the private data that <b>pPrivateDriverData</b> points to.


### -field hContext

[out] A handle to the context that the <a href="https://docs.microsoft.com/previous-versions/ff568895(v=vs.85)">pfnCreateContextCb</a> function creates. 


### -field pCommandBuffer

[out] A pointer to the first command buffer for the created context.


### -field CommandBufferSize

[out] The size, in bytes, of the first command buffer for the created context, which <b>pCommandBuffer</b> points to. 


### -field pAllocationList

[out] An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_allocationlist">D3DDDI_ALLOCATIONLIST</a> structures for the first allocation list for the created context.


### -field AllocationListSize

[out] The number of elements in the allocation-list array that <b>pAllocationList</b> specifies.


### -field pPatchLocationList

[out] An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_patchlocationlist">D3DDDI_PATCHLOCATIONLIST</a> structures for the first patch-location list for the created context.


### -field PatchLocationListSize

[out] The number of elements in the patch-location-list array that <b>pPatchLocationList</b> specifies.


### -field CommandBuffer

This member is reserved and should be set to zero.

This member is available beginning with Windows 7.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_allocationlist">D3DDDI_ALLOCATIONLIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_createcontextflags">D3DDDI_CREATECONTEXTFLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_patchlocationlist">D3DDDI_PATCHLOCATIONLIST</a>



<a href="https://docs.microsoft.com/previous-versions/ff568895(v=vs.85)">pfnCreateContextCb</a>
 

 

