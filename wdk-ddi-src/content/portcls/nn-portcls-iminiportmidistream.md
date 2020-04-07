---
UID: NN:portcls.IMiniportMidiStream
title: IMiniportMidiStream (portcls.h)
description: The IMiniportMidiStream interface represents the MIDI stream that flows through a pin on a MIDI filter.
old-location: audio\iminiportmidistream.htm
tech.root: audio
ms.assetid: a3b763af-2800-4e6d-b9f8-060ba80de7e6
ms.date: 05/08/2018
keywords: ["IMiniportMidiStream interface"]
ms.keywords: IMiniportMidiStream, IMiniportMidiStream interface [Audio Devices], IMiniportMidiStream interface [Audio Devices],described, audio.iminiportmidistream, audmp-routines_604abeae-e44f-418a-913f-39502b6f266b.xml, portcls/IMiniportMidiStream
f1_keywords:
 - "portcls/IMiniportMidiStream"
req.header: portcls.h
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
- COM
api_location:
- portcls.h
api_name:
- IMiniportMidiStream
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportMidiStream interface


## -description


The <code>IMiniportMidiStream</code> interface represents the MIDI stream that flows through a pin on a MIDI filter. The filter wraps a MIDI synthesizer or capture device and is implemented by pairing a MIDI port driver with a MIDI miniport driver. The miniport driver implements the <code>IMiniportMidiStream</code> interface and exposes it to the port driver. The port driver creates a stream object with this interface by calling the miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportmidi-newstream">IMiniportMidi::NewStream</a> method. <code>IMiniportMidiStream</code> inherits from the <b>IUnknown</b> interface.

 This interface provides methods for reading and writing a MIDI stream and for setting the format and state of a MIDI stream.

