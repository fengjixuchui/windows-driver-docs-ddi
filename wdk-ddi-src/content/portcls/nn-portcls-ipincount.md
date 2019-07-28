---
UID: NN:portcls.IPinCount
title: IPinCount (portcls.h)
description: The IPinCount interface provides a means for the miniport driver to monitor and manipulate its pin counts dynamically as pins are instantiated and closed.
old-location: audio\ipincount.htm
tech.root: audio
ms.assetid: 9e02584a-4c65-4400-b06e-58ba095c8dd0
ms.date: 05/08/2018
ms.keywords: IPinCount, IPinCount interface [Audio Devices], IPinCount interface [Audio Devices],described, audio.ipincount, audmp-routines_05698591-4c80-4f02-a420-a87afff949ad.xml, portcls/IPinCount
ms.topic: interface
f1_keywords:
 - "portcls/IPinCount"
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
- IPinCount
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPinCount interface


## -description


The <code>IPinCount</code> interface provides a means for the miniport driver to monitor and manipulate its pin counts dynamically as pins are instantiated and closed. This interface is implemented in the miniport driver. To determine whether a miniport driver supports this interface, the port driver calls the miniport object's <b>QueryInterface</b> method with REFIID <b>IID_IPinCount</b>. <code>IPinCount</code> inherits from the <b>IUnknown</b> interface.

The following port drivers will use a miniport driver's <code>IPinCount</code> interface if the miniport driver implements it: WaveCyclic, WavePci, MIDI, DMus, and Topology.

<code>IPinCount</code> is an optional interface that a miniport driver can support if it needs to do either or both of the following:
<ul>
<li>
Be explicitly notified of changes in kernel streaming pin counts.

</li>
<li>
Dynamically change its pin counts.

</li>
</ul>In the case of a wave audio device, for example, streams with different attributes (3D, stereo/mono, and so on) might also have different "weights" in terms of the amount of hardware resources they consume.

When opening a "heavyweight" stream, the miniport driver might need to decrement the available pin count by two instead of by one in order to more accurately indicate the number of pins that can be created with the remaining resources.

The process is reversed when a "heavyweight" stream is closed. The available pin count might increase by more than one in order to reflect the fact that two or more "lightweight" streams can be created from the newly freed resources.

If a miniport driver does not support the <code>IPinCount</code> interface, the port driver uses the statically initialized pin counts in the filter's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/ns-portcls-pcpin_descriptor">PCPIN_DESCRIPTOR</a> array.

The <code>IPinCount</code> interface provides a single method. The port driver that is bound to the miniport driver calls this method in response to a pin-count query.

