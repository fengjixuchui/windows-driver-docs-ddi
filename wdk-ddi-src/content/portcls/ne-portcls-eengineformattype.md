---
UID: NE:portcls.__unnamed_enum_4
title: eEngineFormatType (portcls.h)
description: The eEngineFormatType enumeration defines constants that specify the audio data type supported by the audio engine.
old-location: audio\eengineformattype.htm
tech.root: audio
ms.assetid: C16DE51F-6552-4379-B866-D7653B1BA9F2
ms.date: 05/08/2018
keywords: ["eEngineFormatType enumeration"]
ms.keywords: audio.eengineformattype, eDeviceFormat, eEngineFormatType, eEngineFormatType enumeration [Audio Devices], eMixFormat, eSupportedDeviceFormats, portcls/eDeviceFormat, portcls/eEngineFormatType, portcls/eMixFormat, portcls/eSupportedDeviceFormats
f1_keywords:
 - "portcls/eEngineFormatType"
req.header: portcls.h
req.include-header: 
req.target-type: Windows
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
- HeaderDef
api_location:
- Portcls.h
api_name:
- eEngineFormatType
product:
- Windows
targetos: Windows
req.typenames: eEngineFormatType
---

# eEngineFormatType enumeration


## -description


The <b>eEngineFormatType</b> enumeration defines constants that specify the audio data type supported by the audio engine.


## -enum-fields




### -field eMixFormat

Indicates a data format for the Mixer.


### -field eDeviceFormat

Indicates the default data format for the audio adapter.


### -field eSupportedDeviceFormats

Indicates all the data formats supported by the audio adapter.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportaudioenginenode-getengineformatsize">GetEngineFormatSize</a>
 

 

