---
UID: NN:portcls.IMiniportWavePciStream
title: IMiniportWavePciStream (portcls.h)
description: The IMiniportWavePciStream interface represents the wave stream that flows through a pin on a WavePci filter.
old-location: audio\iminiportwavepcistream.htm
tech.root: audio
ms.assetid: 2341f914-d877-4a87-ac74-fb51e646510e
ms.date: 05/08/2018
keywords: ["IMiniportWavePciStream interface"]
ms.keywords: IMiniportWavePciStream, IMiniportWavePciStream interface [Audio Devices], IMiniportWavePciStream interface [Audio Devices],described, audio.iminiportwavepcistream, audmp-routines_4bb3e6fe-950d-4981-a35a-bc9106d98edb.xml, portcls/IMiniportWavePciStream
f1_keywords:
 - "portcls/IMiniportWavePciStream"
 - "IMiniportWavePciStream"
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
- IMiniportWavePciStream
targetos: Windows
req.typenames: 
---

# IMiniportWavePciStream interface


## -description


The <code>IMiniportWavePciStream</code> interface represents the wave stream that flows through a pin on a WavePci filter. The filter wraps a WavePci rendering or capture device and is implemented by pairing a WavePci port driver with a WavePci miniport driver. The miniport driver implements the <code>IMiniportWavePciStream</code> interface and exposes it to the port driver. The miniport driver creates a stream object with this interface when the port driver calls the miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavepci-newstream">IMiniportWavePci::NewStream</a> method. <code>IMiniportWavePciStream</code> inherits from the <b>IUnknown</b> interface.

The <code>IMiniportWavePciStream</code> interface provides methods for managing a single stream of incoming or outgoing audio wave data. This is the interface that exposes most of the miniport driver's functionality.

