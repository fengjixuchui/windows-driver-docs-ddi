---
UID: NN:portcls.IPortWavePciStream
title: IPortWavePciStream (portcls.h)
description: The IPortWavePciStream interface is the stream-associated callback interface that provides mapping services to WavePci miniport stream objects.
old-location: audio\iportwavepcistream.htm
tech.root: audio
ms.assetid: c59ea7d7-17f1-4751-a948-387d7568b832
ms.date: 05/08/2018
keywords: ["IPortWavePciStream interface"]
ms.keywords: IPortWavePciStream, IPortWavePciStream interface [Audio Devices], IPortWavePciStream interface [Audio Devices],described, audio.iportwavepcistream, audmp-routines_2ccb79d5-48b9-4b7b-8656-0d427ae99c22.xml, portcls/IPortWavePciStream
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPortWavePciStream
 - portcls/IPortWavePciStream
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IPortWavePciStream
---

# IPortWavePciStream interface


## -description

The <code>IPortWavePciStream</code> interface is the stream-associated callback interface that provides mapping services to WavePci miniport stream objects. The WavePci port driver implements this interface and exposes it to the miniport driver. The port driver provides a reference to an <code>IPortWavePciStream</code> object to each miniport stream object that it creates. <code>IPortWavePciStream</code> inherits from the <b>IUnknown</b> interface.

The stream is associated with a pin on the WavePci filter, which the adapter driver forms by binding the port and miniport drivers. The port driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavepci-newstream">IMiniportWavePci::NewStream</a> method to create the miniport stream object; the port driver passes an <code>IPortWavePciStream</code> reference as one of the call parameters.

