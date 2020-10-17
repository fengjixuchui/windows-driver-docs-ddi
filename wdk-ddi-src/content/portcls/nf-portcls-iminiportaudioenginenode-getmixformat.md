---
UID: NF:portcls.IMiniportAudioEngineNode.GetMixFormat
title: IMiniportAudioEngineNode::GetMixFormat (portcls.h)
description: Gets the audio data format for the audio engine mixer.
old-location: audio\iminiportaudioenginenode_getmixformat.htm
tech.root: audio
ms.assetid: CB0DD6C8-DFB3-42E0-B38F-341677A72E29
ms.date: 05/08/2018
keywords: ["IMiniportAudioEngineNode::GetMixFormat"]
ms.keywords: GetMixFormat, GetMixFormat method [Audio Devices], GetMixFormat method [Audio Devices],IMiniportAudioEngineNode interface, IMiniportAudioEngineNode interface [Audio Devices],GetMixFormat method, IMiniportAudioEngineNode.GetMixFormat, IMiniportAudioEngineNode::GetMixFormat, audio.iminiportaudioenginenode_getmixformat, portcls/IMiniportAudioEngineNode::GetMixFormat
req.header: portcls.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
 - IMiniportAudioEngineNode::GetMixFormat
 - portcls/IMiniportAudioEngineNode::GetMixFormat
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Portcls.h
api_name:
 - IMiniportAudioEngineNode.GetMixFormat
---

# IMiniportAudioEngineNode::GetMixFormat


## -description

Gets the audio data format for the audio engine mixer.

## -parameters

### -param ulNodeId 

[in]
The ID of the mixer node.

### -param pFormat 

[out]
A structure of type <a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksdataformat_waveformatex">KSDATAFORMAT_WAVEFORMATEX</a> that represents the audio data format.

### -param ulBufferSize 

[in]
The data buffer size.

## -returns

<b>GetMixFormat</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportaudioenginenode">IMiniportAudioEngineNode</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksdataformat_waveformatex">KSDATAFORMAT_WAVEFORMATEX</a>