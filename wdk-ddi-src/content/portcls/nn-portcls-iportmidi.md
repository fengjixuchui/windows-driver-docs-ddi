---
UID: NN:portcls.IPortMidi
title: IPortMidi (portcls.h)
description: The IPortMidi interface is the MIDI port driver's primary interface.
old-location: audio\iportmidi.htm
tech.root: audio
ms.assetid: e5403377-fd24-4fd5-8158-194f30238c44
ms.date: 05/08/2018
keywords: ["IPortMidi interface"]
ms.keywords: IPortMidi, IPortMidi interface [Audio Devices], IPortMidi interface [Audio Devices],described, audio.iportmidi, audmp-routines_52a1c6a3-7658-4c69-a4c9-6d965a1d99c9.xml, portcls/IPortMidi
f1_keywords:
 - "portcls/IPortMidi"
 - "IPortMidi"
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
- IPortMidi
targetos: Windows
req.typenames: 
---

# IPortMidi interface


## -description


The <code>IPortMidi</code> interface is the MIDI port driver's primary interface. The PortCls system driver implements this interface and exposes it to the adapter driver that implements the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportmidi">IMiniportMidi</a> object. An adapter driver creates an <code>IPortMidi</code> object by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcnewport">PcNewPort</a> and specifying REFIID <b>IID_IPortMidi</b>. <code>IPortMidi</code> inherits from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iport">IPort</a> interface.

An adapter driver forms a miniport/port driver pair by binding an <b>IMiniportMidi</b> object to an <code>IPortMidi</code> object. The PortCls system driver registers this pair with the system as a MIDI filter (see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/midi-and-directmusic-filters">MIDI and DirectMusic Filters</a>).

