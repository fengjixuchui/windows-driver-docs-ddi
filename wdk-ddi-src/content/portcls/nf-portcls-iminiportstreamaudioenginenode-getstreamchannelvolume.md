---
UID: NF:portcls.IMiniportStreamAudioEngineNode.GetStreamChannelVolume
title: IMiniportStreamAudioEngineNode::GetStreamChannelVolume (portcls.h)
description: Gets the current volume level that is applied to the audio stream.
old-location: audio\iminiportstreamaudioenginenode_getstreamchannelvolume.htm
tech.root: audio
ms.assetid: 0BD6FCB7-1705-4343-AD41-7362FE095ECB
ms.date: 05/08/2018
keywords: ["IMiniportStreamAudioEngineNode::GetStreamChannelVolume"]
ms.keywords: GetStreamChannelVolume, GetStreamChannelVolume method [Audio Devices], GetStreamChannelVolume method [Audio Devices],IMiniportStreamAudioEngineNode interface, IMiniportStreamAudioEngineNode interface [Audio Devices],GetStreamChannelVolume method, IMiniportStreamAudioEngineNode.GetStreamChannelVolume, IMiniportStreamAudioEngineNode::GetStreamChannelVolume, audio.iminiportstreamaudioenginenode_getstreamchannelvolume, portcls/IMiniportStreamAudioEngineNode::GetStreamChannelVolume
f1_keywords:
 - "portcls/IMiniportStreamAudioEngineNode.GetStreamChannelVolume"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Portcls.h
api_name:
- IMiniportStreamAudioEngineNode.GetStreamChannelVolume
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportStreamAudioEngineNode::GetStreamChannelVolume


## -description


Gets the current volume level that is applied to the audio stream.


## -parameters




### -param ulChannel [in]

The audio stream channel.


### -param plValue [out]

The current volume level.


## -returns



<b>GetStreamChannelVolume</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportstreamaudioenginenode">IMiniportStreamAudioEngineNode</a>
 

 

