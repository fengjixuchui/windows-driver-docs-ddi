---
UID: NS:d3d12umddi.D3D12DDI_COMMAND_LIST_FUNCS_3D_0033
title: D3D12DDI_COMMAND_LIST_FUNCS_3D_0033 (d3d12umddi.h)
description: The command list functions for 3D.
old-location: display\d3d12ddi-command-list-funcs-3d-0033.htm
ms.assetid: 421e0623-0679-4068-b8e0-f0278abd2caf
ms.date: 05/10/2018
keywords: ["D3D12DDI_COMMAND_LIST_FUNCS_3D_0033 structure"]
ms.keywords: D3D12DDI_COMMAND_LIST_FUNCS_3D_0033, D3D12DDI_COMMAND_LIST_FUNCS_3D_0033 structure [Display Devices], d3d12umddi/D3D12DDI_COMMAND_LIST_FUNCS_3D_0033, display.d3d12ddi-command-list-funcs-3d-0033
f1_keywords:
 - "d3d12umddi/D3D12DDI_COMMAND_LIST_FUNCS_3D_0033"
 - "D3D12DDI_COMMAND_LIST_FUNCS_3D_0033"
req.header: d3d12umddi.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d12umddi.h
api_name:
- D3D12DDI_COMMAND_LIST_FUNCS_3D_0033
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_COMMAND_LIST_FUNCS_3D_0033
---

# D3D12DDI_COMMAND_LIST_FUNCS_3D_0033 structure


## -description


The command list functions for 3D.


## -struct-fields




### -field pfnCloseCommandList

Close the command list.


### -field pfnResetCommandList

Reset the command list.


### -field pfnDrawInstanced

Draw instanced.


### -field pfnDrawIndexedInstanced

Draw indexed instanced.


### -field pfnDispatch

Dispatch.


### -field pfnClearUnorderedAccessViewUint

Clear unordered access view unit.


### -field pfnClearUnorderedAccessViewFloat

Clear unordered access view float.


### -field pfnClearRenderTargetView

Clear render target view.


### -field pfnClearDepthStencilView

Clear depth stencil view.


### -field pfnDiscardResource

Discard resource.


### -field pfnCopyTextureRegion

Copy texture region.


### -field pfnResourceCopy

Resource copy.


### -field pfnCopyTiles

Copy tiles.


### -field pfnCopyBufferRegion

Copy buffer region.


### -field pfnResourceResolveSubresource

Resource resolve subresource.


### -field pfnExecuteBundle

Execute bundle.


### -field pfnExecuteIndirect

Execute indirect.


### -field pfnResourceBarrier

Resource barrier.


### -field pfnBlt

Blt.


### -field pfnPresent

Present.


### -field pfnBeginQuery

Begin query.


### -field pfnEndQuery

End query.


### -field pfnResolveQueryData

Resolve query data.


### -field pfnSetPredication

Set predication.


### -field pfnIaSetTopology

Set topology


### -field pfnRsSetViewports

Set view ports.


### -field pfnRsSetScissorRects

Set scissor rectangles.


### -field pfnOmSetBlendFactor

Set blend factor.


### -field pfnOmSetStencilRef

Set stencil reference.


### -field pfnSetPipelineState

Set pipeline state.


### -field pfnSetDescriptorHeaps

Set descriptor heaps.


### -field pfnSetComputeRootSignature

Set compute root signature.


### -field pfnSetGraphicsRootSignature

Set graphics root signature.


### -field pfnSetComputeRootDescriptorTable

Set compute root descriptor table.


### -field pfnSetGraphicsRootDescriptorTable

Set graphics root descriptor table.


### -field pfnSetComputeRoot32BitConstant

Set compute root 32-bit constant.


### -field pfnSetGraphicsRoot32BitConstant

Set graphics root 32-bit constant.


### -field pfnSetComputeRoot32BitConstants

Set compute root 32-bit constants.


### -field pfnSetGraphicsRoot32BitConstants

Set graphics root 32-bit constants.


### -field pfnSetComputeRootConstantBufferView

Set compute root constant buffer view.


### -field pfnSetGraphicsRootConstantBufferView

Set graphics root constant buffer view.


### -field pfnSetComputeRootShaderResourceView

Set compute root shader resource view.


### -field pfnSetGraphicsRootShaderResourceView

Set graphics root shader resource view.


### -field pfnSetComputeRootUnorderedAccessView

Set compute root unordered access view.


### -field pfnSetGraphicsRootUnorderedAccessView

Set graphics root unordered access view.


### -field pfnIASetIndexBuffer

Set index buffer.


### -field pfnIASetVertexBuffers

Set vertex buffers.


### -field pfnSOSetTargets

Set targets.


### -field pfnOMSetRenderTargets

Set render targets.


### -field pfnSetMarker

Set marker.


### -field pfnClearRootArguments

Clear root arguments.


### -field pfnAtomicCopyBufferRegion

Atomic copy buffer region.


### -field pfnOMSetDepthBounds

Set depth bounds.


### -field pfnSetSamplePositions

Set sample positions.


### -field pfnResourceResolveSubresourceRegion

Resource resolve subresource region.


### -field pfnSetProtectedResourceSession

Set protected resource session.


### -field pfnWriteBufferImmediate

Write buffer immediate.


### -field pfnSetViewInstanceMask

Set view instance mask.

