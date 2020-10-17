---
UID: NF:portcls.IMiniportMidiStream.SetState
title: IMiniportMidiStream::SetState (portcls.h)
description: The SetState method sets the stream's transport state to a new state value.
old-location: audio\iminiportmidistream_setstate.htm
tech.root: audio
ms.assetid: ee78013c-7660-4017-97ec-eff9068b707a
ms.date: 05/08/2018
keywords: ["IMiniportMidiStream::SetState"]
ms.keywords: IMiniportMidiStream interface [Audio Devices],SetState method, IMiniportMidiStream.SetState, IMiniportMidiStream::SetState, SetState, SetState method [Audio Devices], SetState method [Audio Devices],IMiniportMidiStream interface, audio.iminiportmidistream_setstate, audmp-routines_23f064df-faef-4c45-a58e-c5e3e1d7d7a5.xml, portcls/IMiniportMidiStream::SetState
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IMiniportMidiStream::SetState
 - portcls/IMiniportMidiStream::SetState
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IMiniportMidiStream.SetState
---

# IMiniportMidiStream::SetState


## -description

The <code>SetState</code> method sets the stream's transport state to a new state value.

## -parameters

### -param State 

[in]
Specifies the new state that the stream is to be set to. This parameter is a <a href="/windows-hardware/drivers/ddi/ks/ne-ks-ksstate">KSSTATE</a> enumeration value. For more information, see the following Remarks section.

## -returns

<code>SetState</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## -remarks

For an audio filter graph, the four <a href="/windows-hardware/drivers/ddi/ks/ne-ks-ksstate">KSSTATE</a> enumeration values are interpreted as follows:

<ul>
<li>
KSSTATE_RUN 

Data transport in the current audio filter graph is running and functioning as normal.

</li>
<li>
KSSTATE_ACQUIRE 

This is a transitional state that helps to manage the transition between KSSTATE_RUN and KSSTATE_STOP.

</li>
<li>
KSSTATE_PAUSE 

This is a transitional state that helps to manage the transition between KSSTATE_RUN and KSSTATE_STOP. 

</li>
<li>
KSSTATE_STOP 

Data transport is stopped in the current audio filter graph.

</li>
</ul>
For most miniport drivers, KSSTATE_ACQUIRE and KSSTATE_PAUSE are indistinguishable. The <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportmidi-newstream">IMiniportMidi::NewStream</a> method sets the initial state of the stream to KSSTATE_STOP.

Transitions always occur in one of the following two sequences:

<ul>
<li>
STOP -> ACQUIRE -> PAUSE -> RUN

</li>
<li>
RUN -> PAUSE -> ACQUIRE -> STOP

</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportmidi-newstream">IMiniportMidi::NewStream</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportmidistream">IMiniportMidiStream</a>



<a href="/windows-hardware/drivers/stream/ksproperty-connection-state">KSPROPERTY_CONNECTION_STATE</a>



<a href="/windows-hardware/drivers/ddi/ks/ne-ks-ksstate">KSSTATE</a>