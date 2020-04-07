---
UID: NF:portcls.IMiniportAudioEngineNode.GetDeviceChannelVolume
title: IMiniportAudioEngineNode::GetDeviceChannelVolume (portcls.h)
description: Gets the volume level for a given channel of the audio device.
old-location: audio\iminiportaudioenginenode_getdevicechannelvolume.htm
tech.root: audio
ms.assetid: 195AAD37-6993-4F0A-BEF7-848122402742
ms.date: 05/08/2018
keywords: ["IMiniportAudioEngineNode::GetDeviceChannelVolume"]
ms.keywords: GetDeviceChannelVolume, GetDeviceChannelVolume method [Audio Devices], GetDeviceChannelVolume method [Audio Devices],IMiniportAudioEngineNode interface, IMiniportAudioEngineNode interface [Audio Devices],GetDeviceChannelVolume method, IMiniportAudioEngineNode.GetDeviceChannelVolume, IMiniportAudioEngineNode::GetDeviceChannelVolume, audio.iminiportaudioenginenode_getdevicechannelvolume, portcls/IMiniportAudioEngineNode::GetDeviceChannelVolume
f1_keywords:
 - "portcls/IMiniportAudioEngineNode.GetDeviceChannelVolume"
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
- IMiniportAudioEngineNode.GetDeviceChannelVolume
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportAudioEngineNode::GetDeviceChannelVolume


## -description


Gets the volume level for a given channel of the audio device.


## -parameters




### -param ulNodeId [in]

The ID for the node that represents the audio device.


### -param ulChannel [in]

The audio device channel.


### -param plVolume [out]

The current volume level for the audio device channel.


## -returns



<b>GetDeviceChannelVolume</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportaudioenginenode">IMiniportAudioEngineNode</a>
 

 

