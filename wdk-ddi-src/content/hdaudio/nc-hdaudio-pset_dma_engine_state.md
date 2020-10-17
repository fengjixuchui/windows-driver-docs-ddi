---
UID: NC:hdaudio.PSET_DMA_ENGINE_STATE
title: PSET_DMA_ENGINE_STATE (hdaudio.h)
description: The SetDmaEngineState routine sets the state of one or more DMA engines to the Running, Stopped, Paused, or Reset state.The function pointer type for a SetDmaEngineState routine is defined as follows.
old-location: audio\setdmaenginestate.htm
tech.root: audio
ms.assetid: 05cfb827-e143-4d77-b378-e02dd381e429
ms.date: 05/08/2018
keywords: ["PSET_DMA_ENGINE_STATE callback function"]
ms.keywords: PSET_DMA_ENGINE_STATE, PSET_DMA_ENGINE_STATE callback, SetDmaEngineState, SetDmaEngineState callback function [Audio Devices], aud-prop2_a1455dc1-3ed9-43c3-a5b6-af321c26eefe.xml, audio.setdmaenginestate, hdaudio/SetDmaEngineState
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PSET_DMA_ENGINE_STATE
 - hdaudio/PSET_DMA_ENGINE_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - hdaudio.h
api_name:
 - SetDmaEngineState
---

# PSET_DMA_ENGINE_STATE callback function


## -description

The <i>SetDmaEngineState</i> routine sets the state of one or more DMA engines to the Running, Stopped, Paused, or Reset state.

The function pointer type for a <i>SetDmaEngineState</i> routine is defined as follows.

## -parameters

### -param _context 

[in]
Specifies the context value from the <b>Context</b> member of the <a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a><u>, </u><a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a>, or <a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_bdl">HDAUDIO_BUS_INTERFACE_BDL</a> structure.

### -param StreamState

### -param NumberOfHandles 

[in]
Specifies the number of handles in the <i>handles</i> array. Set this parameter to a nonzero value.

### -param Handles 

[in]
Pointer to an array of handles to DMA engines. Specify a non-<b>NULL</b> value for this parameter.


#### - streamState [in]

Specifies the new stream state. Set this parameter to one of the following HDAUDIO_STREAM_STATE enumeration values:

<ul>
<li>
<b>PauseState</b> (paused)

</li>
<li>
<b>ResetState</b> (reset)

</li>
<li>
<b>RunState</b> (running)

</li>
<li>
<b>StopState</b> (stopped)

</li>
</ul>
In the current implementation, <b>PauseState</b> and <b>StopState</b> represent the same hardware state.

## -returns

<i>SetDmaEngineState</i> returns STATUS_SUCCESS if the call succeeds in changing the DMA engines' states. Otherwise, the routine returns an appropriate error code. The following table shows some of the possible return status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
Indicates that one of the handles is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Indicates that one of the parameter values is incorrect (invalid parameter value or bad pointer).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
Indicates that no buffer is currently allocated for one of the DMA engines.

</td>
</tr>
</table>

## -remarks

This routine changes the state of one or more DMA engines to the state that the <i>streamState</i> parameter specifies. The routine synchronizes the state transitions of all the DMA engines that the handles in the <i>handles</i> array identify. For more information, see <a href="/windows-hardware/drivers/audio/synchronizing-two-or-more-streams">Synchronizing Two or More Streams</a>.

Before calling this routine, set up each DMA engine in the <i>handles</i> array:

<ul>
<li>
If using the HDAUDIO_BUS_INTERFACE version of the HD Audio DDI, call <a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_dma_buffer">AllocateDmaBuffer</a> to set up the DMA engine.

</li>
<li>
If using the HDAUDIO_BUS_INTERFACE_BDL version of the DDI, call <a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-psetup_dma_engine_with_bdl">SetupDmaEngineWithBdl</a> to set up the DMA engine.

</li>
</ul>
If no DMA buffer is currently allocated for any DMA engine in the <i>handles</i> array, an attempt to change the stream to any state other than Reset causes the <i>SetDmaEngineState</i> call to fail and return error code STATUS_INVALID_DEVICE_REQUEST.

The stream state cannot transition directly between Running and Reset. Instead, the stream must first pass through an intermediate state of Paused or Stopped:

<ul>
<li>
From a Running or Reset state, the stream state can change directly to either Paused or Stopped.

</li>
<li>
From a paused or stopped state, the stream state can change directly to either Running or Reset.

</li>
</ul>
A WDM audio driver calls this routine during a call to its <b>SetState</b> method. For example, see <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavecyclicstream-setstate">IMiniportWaveCyclicStream::SetState</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pallocate_dma_buffer">AllocateDmaBuffer</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_bdl">HDAUDIO_BUS_INTERFACE_BDL</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavecyclicstream-setstate">IMiniportWaveCyclicStream::SetState</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-psetup_dma_engine_with_bdl">SetupDmaEngineWithBdl</a>