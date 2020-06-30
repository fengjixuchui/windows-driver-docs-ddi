---
UID: NC:hdaudio.PALLOCATE_CONTIGUOUS_DMA_BUFFER
title: PALLOCATE_CONTIGUOUS_DMA_BUFFER (hdaudio.h)
description: The AllocateContiguousDmaBuffer routine allocates a DMA buffer that consists of a single, contiguous block of physical memory.The function pointer type for an AllocateContiguousDmaBuffer routine is defined as follows.
old-location: audio\allocatecontiguousdmabuffer.htm
tech.root: audio
ms.assetid: 4538ce8e-fccd-4862-b226-a99fe578a5fd
ms.date: 05/08/2018
keywords: ["PALLOCATE_CONTIGUOUS_DMA_BUFFER callback function"]
ms.keywords: AllocateContiguousDmaBuffer, AllocateContiguousDmaBuffer callback function [Audio Devices], PALLOCATE_CONTIGUOUS_DMA_BUFFER, PALLOCATE_CONTIGUOUS_DMA_BUFFER callback, aud-prop2_c9f2fa85-0967-4793-9092-9f95986c2126.xml, audio.allocatecontiguousdmabuffer, hdaudio/AllocateContiguousDmaBuffer
f1_keywords:
 - "hdaudio/AllocateContiguousDmaBuffer"
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- hdaudio.h
api_name:
- AllocateContiguousDmaBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# PALLOCATE_CONTIGUOUS_DMA_BUFFER callback function


## -description


The <code>AllocateContiguousDmaBuffer</code> routine allocates a DMA buffer that consists of a single, contiguous block of physical memory.

The function pointer type for an <code>AllocateContiguousDmaBuffer</code> routine is defined as follows.


## -parameters




### -param _context [in]

Specifies the context value from the <b>Context</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_bdl">HDAUDIO_BUS_INTERFACE_BDL</a> structure.


### -param Handle [in]

Handle identifying the DMA engine. This handle value was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_capture_dma_engine">AllocateCaptureDmaEngine</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_render_dma_engine">AllocateRenderDmaEngine</a>.


### -param RequestedBufferSize

Specifies the requested buffer size in bytes.


### -param DataBuffer [out]

Retrieves the data buffer. This parameter points to a caller-allocated PVOID variable into which the routine writes the system virtual address of the data buffer.


### -param BdlBuffer [out]

Retrieves the buffer descriptor list (BDL). This parameter points to a caller-allocated PVOID variable into which the routine writes the system virtual address of the BDL. The BDL allocation size is exactly one memory page and the BDL begins on a page boundary.


## -returns



<code>AllocateContiguousDmaBuffer</code> returns STATUS_SUCCESS if the call succeeds. Otherwise, the routine returns an appropriate error code. The following table shows some of the possible return status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the caller is running at an interrupt request level (IRQL) that is too high.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates that buffer allocation failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the handle parameter value is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Indicates that one of the parameter values is incorrect (bad pointer).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_NOT_READY</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the hardware programming timed out. If this occurs, the hardware might be in a compromised state.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the stream is not in the reset state or that a buffer is already allocated for the DMA engine.

</td>
</tr>
</table>
 




## -remarks



The <code>AllocateContiguousDmaBuffer</code> routine is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-psetup_dma_engine_with_bdl">SetupDmaEngineWithBdl</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_contiguous_dma_buffer">FreeContiguousDmaBuffer</a> routines. These three routines are available only in the HDAUDIO_BUS_INTERFACE_BDL version of the HD Audio DDI. This DDI does not include the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_dma_buffer">AllocateDmaBuffer</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_dma_buffer">FreeDmaBuffer</a> routines, which are never used in conjunction with <code>AllocateContiguousDmaBuffer</code>, <b>SetupDmaEngineWithBdl</b>, and <b>FreeContiguousDmaBuffer</b>. Unlike <b>SetupDmaEngineWithBdl</b>, which configures the DMA engine to use a previously allocated DMA buffer, <code>AllocateDmaBuffer</code> both allocates a DMA buffer and configures the DMA engine to use the buffer. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/differences-between-the-hd-audio-ddi-versions">Differences between the Two DDI Versions</a>.

<code>AllocateContiguousDmaBuffer</code> allocates a data buffer for the specified DMA engine. It also allocates a page of memory for the BDL. Depending on the host processor architecture, a typical page size might be 4,096 or 8,192 bytes. The data buffer consists of a single, contiguous block of physical memory.

The handle parameter specifies the DMA engine that is to use the data buffer and BDL. The routine allocates storage that meets the DMA engine's size, alignment, and position requirements.

The storage that the routine allocates for the data buffer and BDL is uninitialized. The function driver is responsible for filling in the BDL before submitting it to the <b>SetupDmaEngineWithBdl</b> routine. The function driver is also responsible for programming the codec to manage the data transfers and to recognize the stream identifier.

To generate IOC interrupts at precise intervals, the function driver might be required to divide the data buffer allocation into several fragments of a particular size. Each fragment is described by a BDL entry. The fragment size can be adjusted to tune the interrupt rate. According to the Intel High Definition Audio Specification (see the <a href="https://go.microsoft.com/fwlink/p/?linkid=42508">Intel HD Audio</a> website), each fragment must begin on a 128-byte boundary, although no such alignment requirement applies to the length of the fragment. Thus, a gap might exist between the end of one fragment and the beginning of the next. When calling <b>SetupDmaEngineWithBdl</b>, the function driver must specify a value for the <i>bufferSize</i> parameter that represents the sum of the sizes of the individual fragments that the BDL entries describe. This size will be less than or equal to the number of bytes specified in the <code>AllocateContiguousDmaBuffer</code> routine's <i>requestedBufferSize</i> parameter.

During the lifetime of a DMA engine handle, <code>AllocateContiguousDmaBuffer</code> can be called successively to allocate new DMA buffers. However, before calling <code>AllocateContiguousDmaBuffer</code>, any previously allocated DMA buffer must first be freed by calling <b>FreeContiguousDmaBuffer</b>.

During calls to <code>AllocateContiguousDmaBuffer</code>, <b>SetupDmaEngineWithBdl</b>, and <b>FreeContiguousDmaBuffer</b>, the DMA engine must be in the reset stream state. The DMA engine is in the reset state immediately following the call to Allocate<i>Xxx</i>DmaEngine. To change the DMA engine to the run state, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pset_dma_engine_state">SetDmaEngineState</a>.

This routine fails and returns error code STATUS_INVALID_DEVICE_REQUEST in either of the following circumstances:

<ul>
<li>
Any previously allocated DMA buffer has not been freed (by calling <b>FreeContiguousDmaBuffer</b>).

</li>
<li>
The stream is in a state other than reset.

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_capture_dma_engine">AllocateCaptureDmaEngine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_dma_buffer">AllocateDmaBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_render_dma_engine">AllocateRenderDmaEngine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_contiguous_dma_buffer">FreeContiguousDmaBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pfree_dma_buffer">FreeDmaBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_bdl">HDAUDIO_BUS_INTERFACE_BDL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pset_dma_engine_state">SetDmaEngineState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-psetup_dma_engine_with_bdl">SetupDmaEngineWithBdl</a>
 

 

