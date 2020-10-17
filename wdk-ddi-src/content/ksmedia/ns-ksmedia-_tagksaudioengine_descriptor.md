---
UID: NS:ksmedia._tagKSAUDIOENGINE_DESCRIPTOR
title: _tagKSAUDIOENGINE_DESCRIPTOR (ksmedia.h)
description: The KSAUDIOENGINE_DESCRIPTOR structure describes the static, external properties of the audio engine.
old-location: audio\ksaudioengine_descriptor.htm
tech.root: audio
ms.assetid: 6691AB8B-EC6E-483B-A10A-6F9C5A97FEC9
ms.date: 05/08/2018
keywords: ["tagKSAUDIOENGINE_DESCRIPTOR structure"]
ms.keywords: "*PKSAUDIOENGINE_DESCRIPTOR, KSAUDIOENGINE_DESCRIPTOR, KSAUDIOENGINE_DESCRIPTOR structure [Audio Devices], PKSAUDIOENGINE_DESCRIPTOR, PKSAUDIOENGINE_DESCRIPTOR structure pointer [Audio Devices], _tagKSAUDIOENGINE_DESCRIPTOR, audio.ksaudioengine_descriptor, ksmedia/KSAUDIOENGINE_DESCRIPTOR, ksmedia/PKSAUDIOENGINE_DESCRIPTOR"
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
req.typenames: KSAUDIOENGINE_DESCRIPTOR, *PKSAUDIOENGINE_DESCRIPTOR
f1_keywords:
 - _tagKSAUDIOENGINE_DESCRIPTOR
 - ksmedia/_tagKSAUDIOENGINE_DESCRIPTOR
 - PKSAUDIOENGINE_DESCRIPTOR
 - ksmedia/PKSAUDIOENGINE_DESCRIPTOR
 - KSAUDIOENGINE_DESCRIPTOR
 - ksmedia/KSAUDIOENGINE_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ksmedia.h
api_name:
 - KSAUDIOENGINE_DESCRIPTOR
---

# _tagKSAUDIOENGINE_DESCRIPTOR structure


## -description

The <b>KSAUDIOENGINE_DESCRIPTOR</b> structure describes the static, external  properties of the audio engine.

## -struct-fields

### -field nHostPinId

Specifies the ID of the pin factory that is connected to the audio engine node that handles host-processed audio data.  This is the pin factory on which a software audio engine will run.

### -field nOffloadPinId

Specifies the ID of the pin factory that is connected to the audio engine node that handles offloaded streams.

### -field nLoopbackPinId

Specifies the ID of the pin factory that is connected to the audio engine node that supplies a post-mix loopback or reference stream.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportaudioenginenode-getaudioenginedescriptor">GetAudioEngineDescriptor</a>



<a href="/windows-hardware/drivers/audio/ksproperty-audioengine-descriptor">KSPROPERTY_AUDIOENGINE_DESCRIPTOR</a>