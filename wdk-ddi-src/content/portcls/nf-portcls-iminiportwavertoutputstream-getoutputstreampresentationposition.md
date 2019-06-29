---
UID: NF:portcls.IMiniportWaveRTOutputStream.GetOutputStreamPresentationPosition
title: IMiniportWaveRTOutputStream::GetOutputStreamPresentationPosition (portcls.h)
description: Returns stream presentation information.
old-location: audio\iminiportwavertoutputstream_getoutputstreampresentationposition.htm
tech.root: audio
ms.assetid: 8E52A10E-5666-41B5-B342-491E5AF9DD38
ms.date: 05/08/2018
ms.keywords: GetOutputStreamPresentationPosition, GetOutputStreamPresentationPosition method [Audio Devices], GetOutputStreamPresentationPosition method [Audio Devices],IMiniportWaveRTOutputStream interface, IMiniportWaveRTOutputStream interface [Audio Devices],GetOutputStreamPresentationPosition method, IMiniportWaveRTOutputStream.GetOutputStreamPresentationPosition, IMiniportWaveRTOutputStream::GetOutputStreamPresentationPosition, audio.iminiportwavertoutputstream_getoutputstreampresentationposition, portcls/IMiniportWaveRTOutputStream::GetOutputStreamPresentationPosition
ms.topic: method
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10 and later.
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
req.irql: Passive level
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- portcls.h
api_name:
- IMiniportWaveRTOutputStream.GetOutputStreamPresentationPosition
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportWaveRTOutputStream::GetOutputStreamPresentationPosition


## -description


Returns stream presentation information.


## -parameters




### -param pPresentationPosition [out]

 pPresentationPosition returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ns-ksmedia-ksaudio_presentation_position">KSAUDIO_PRESENTATION_POSITION</a> structure that represents a recent presentation position in the audio data stream. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iminiportstreamaudioenginenode-getstreampresentationposition">IMiniportStreamAudioEngineNode::GetStreamPresentationPosition</a>.


## -returns



<code>GetOutputStreamPresentationPosition</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the function returns an appropriate error status code.




## -remarks



The OS may periodically get this property from the driver to retrieve recent presentation position information from the driver in order to allow upper layers to synchronize video or other activity with the audio stream.

The value returned in the u64PositionInBlocks member of KSAUDIO_PRESENTATION_POSITION should be consistent with the packet count returned by GetPacketCount and the driver’s interpretation of the packet number passed to SetWritePacket. In other words, the first sample of packet 0 is block 0. 



This does not mean that GetPacketCount and GetOutputStreamPresentationPosition, if called simultaneously, would return values that refer to the same sample. GetPacketCount returns information about the samples transferred from the WaveRT buffer to the hardware, while GetOutputStreamPresentationPosition returns information about samples presented at the output of the system. These are two different pieces of information. 





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iminiportwavertoutputstream">IMiniportWaveRTOutputStream</a>
 

 

