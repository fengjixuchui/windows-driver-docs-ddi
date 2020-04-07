---
UID: NF:portcls.IMiniportAudioEngineNode.GetDeviceChannelPeakMeter
title: IMiniportAudioEngineNode::GetDeviceChannelPeakMeter (portcls.h)
description: Gets the PeakMeter value for the audio device channel.
old-location: audio\iminiportaudioenginenode_getdevicechannelpeakmeter.htm
tech.root: audio
ms.assetid: 31F291ED-0B04-4CDF-A83B-7CF3717EC234
ms.date: 05/08/2018
keywords: ["IMiniportAudioEngineNode::GetDeviceChannelPeakMeter"]
ms.keywords: GetDeviceChannelPeakMeter, GetDeviceChannelPeakMeter method [Audio Devices], GetDeviceChannelPeakMeter method [Audio Devices],IMiniportAudioEngineNode interface, IMiniportAudioEngineNode interface [Audio Devices],GetDeviceChannelPeakMeter method, IMiniportAudioEngineNode.GetDeviceChannelPeakMeter, IMiniportAudioEngineNode::GetDeviceChannelPeakMeter, audio.iminiportaudioenginenode_getdevicechannelpeakmeter, portcls/IMiniportAudioEngineNode::GetDeviceChannelPeakMeter
f1_keywords:
 - "portcls/IMiniportAudioEngineNode.GetDeviceChannelPeakMeter"
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
- IMiniportAudioEngineNode.GetDeviceChannelPeakMeter
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportAudioEngineNode::GetDeviceChannelPeakMeter


## -description


Gets the PeakMeter value  for the audio device channel.


## -parameters




### -param ulNodeId [in]

The ID for the node that represents the audio device.


### -param ulChannel [in]

The audio device channel.


### -param plPeakMeter [out]

The PeakMeter value for the audio device channel.


## -returns



<b>GetDeviceChannelPeakMeter</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportaudioenginenode">IMiniportAudioEngineNode</a>
 

 

