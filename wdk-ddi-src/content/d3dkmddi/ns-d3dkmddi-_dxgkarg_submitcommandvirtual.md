---
UID: NS:d3dkmddi._DXGKARG_SUBMITCOMMANDVIRTUAL
title: _DXGKARG_SUBMITCOMMANDVIRTUAL (d3dkmddi.h)
description: DXGKARG_SUBMITCOMMANDVIRTUAL is used to submit a direct memory access (DMA) buffer to a context that supports virtual addressing with the DxgkDdiSubmitCommandVirtualdevice driver interface (DDI).
old-location: display\dxgkarg_submitcommandvirtual.htm
ms.assetid: 7BBB4BEC-82F1-44B9-A0C2-1073517A4116
ms.date: 05/10/2018
keywords: ["_DXGKARG_SUBMITCOMMANDVIRTUAL structure"]
ms.keywords: DXGKARG_SUBMITCOMMANDVIRTUAL, DXGKARG_SUBMITCOMMANDVIRTUAL structure [Display Devices], _DXGKARG_SUBMITCOMMANDVIRTUAL, d3dkmddi/DXGKARG_SUBMITCOMMANDVIRTUAL, display.dxgkarg_submitcommandvirtual
f1_keywords:
 - "d3dkmddi/DXGKARG_SUBMITCOMMANDVIRTUAL"
 - "DXGKARG_SUBMITCOMMANDVIRTUAL"
req.header: d3dkmddi.h
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
- d3dkmddi.h
api_name:
- DXGKARG_SUBMITCOMMANDVIRTUAL
targetos: Windows
tech.root: display
req.typenames: DXGKARG_SUBMITCOMMANDVIRTUAL
---

# _DXGKARG_SUBMITCOMMANDVIRTUAL structure


## -description


<b>DXGKARG_SUBMITCOMMANDVIRTUAL</b> is used to submit a direct memory access (DMA) buffer to a context that supports virtual addressing with the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_submitcommandvirtual">DxgkDdiSubmitCommandVirtual</a>device driver interface (DDI).




## -struct-fields




### -field hContext

The handle returned from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext">DxgkDdiCreateContext</a>.


### -field DmaBufferVirtualAddress

The virtual address for the DMA buffer in the context of the submitting process.


### -field DmaBufferSize

The size of the DMA buffer in bytes.


### -field pDmaBufferPrivateData

A pointer to the driver-private data buffer.


### -field DmaBufferPrivateDataSize

The size of the driver-private data buffer in bytes.


### -field DmaBufferUmdPrivateDataSize

Size of the private driver data, in bytes, that was set by the user mode driver in <b>SubmitCommandCb</b>. When <b>SubmitCommandCb</b> is called, the DirectX graphics kernel allocates a buffer for the private driver data with the size equal to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_contextinfo">DXGK_CONTEXTINFO</a>::<b>DmaBufferPrivateDataSize</b>. This size was reported by the kernel mode driver in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext">DxgkDdiCreateContext</a> call. The DirectX graphics kernel copies the driver private data from the <b>SubmitCommandCb</b> to the allocated buffer.


### -field SubmissionFenceId

A unique identifier that the driver can write into the fence command in the ring buffer, which is the buffer where DMA buffers are queued for the GPU to run. For more information about these types of identifiers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/supplying-fence-identifiers">Supplying Fence Identifiers</a>.


### -field VidPnSourceId

The zero-based identification number of the video present source in a path of a video present network (VidPN) topology for a flip operation. This member is valid only when the <b>Flip</b> or <b>FlipWithNoWait</b> bit-field flag is set in the <b>Flags</b> member.


### -field FlipInterval

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-d3dddi_flipinterval_type">D3DDDI_FLIPINTERVAL_TYPE</a>-typed value that indicates the flip interval (that is, if the flip occurs after zero, one, two, three, or four vertical syncs). <b>FlipInterval</b> is valid only if the <b>Flip</b> bit-field flag is set (that is, <b>TRUE</b>) in the <b>Flags</b> member.


### -field Flags

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_submitcommandflags">DXGK_SUBMITCOMMANDFLAGS</a> structure that identifies information about the DMA buffer to submit.


### -field EngineOrdinal

Reserved for future use.


### -field NodeOrdinal

The zero-based index of the node that the context is created for. Identifies the node when the context is <b>NULL</b>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-d3dddi_flipinterval_type">D3DDDI_FLIPINTERVAL_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_contextinfo">DXGK_CONTEXTINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext">DxgkDdiCreateContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_submitcommandvirtual">DxgkDdiSubmitCommandVirtual</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/display/supplying-fence-identifiers">Supplying Fence Identifiers</a>
 

 

