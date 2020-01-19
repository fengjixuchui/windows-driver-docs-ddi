---
UID: NN:portcls.IMiniportWaveRTStreamNotification
title: IMiniportWaveRTStreamNotification (portcls.h)
description: The IMiniportWaveRTStreamNotification interface is supported in Windows Vista and later Windows operating systems, and it augments the IMiniportWaveRTStream interface, providing additional methods to facilitate DMA driver event notifications.
old-location: audio\iminiportwavertstreamnotification.htm
tech.root: audio
ms.assetid: e009c459-77f7-43ee-9e95-8408324b0a9b
ms.date: 05/08/2018
ms.keywords: IMiniportWaveRTStreamNotification, IMiniportWaveRTStreamNotification interface [Audio Devices], IMiniportWaveRTStreamNotification interface [Audio Devices],described, audio.iminiportwavertstreamnotification, audmp-routines_a49bf74b-367b-44f4-b8de-a3adf6240b36.xml, portcls/IMiniportWaveRTStreamNotification
ms.topic: interface
f1_keywords:
 - "portcls/IMiniportWaveRTStreamNotification"
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
- IMiniportWaveRTStreamNotification
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportWaveRTStreamNotification interface


## -description


The <code>IMiniportWaveRTStreamNotification</code> interface is supported in Windows Vista and later Windows operating systems, and it augments the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportwavertstream">IMiniportWaveRTStream</a> interface, providing additional methods to facilitate DMA driver event notifications. 

To access the <code>IMiniportWaveRTStreamNotification</code> interface, the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/wavert-port-driver">WaveRT port driver</a> calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavert-newstream">IMiniportWaveRT::NewStream</a> method and receives an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportwavertstream">IMiniportWaveRTStream</a> interface. The WaveRT port driver then queries the <b>IMiniportWaveRTStream</b> interface, uisng QueryInterface, and receives the <code>IMiniportWaveRTStreamNotification</code> interface. 

<code>IMiniportWaveRTStreamNotification</code> inherits from the <b>IUnknown</b> interface.

