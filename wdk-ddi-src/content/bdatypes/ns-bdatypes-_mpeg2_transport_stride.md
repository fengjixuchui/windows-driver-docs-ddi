---
UID: NS:bdatypes._MPEG2_TRANSPORT_STRIDE
title: _MPEG2_TRANSPORT_STRIDE (bdatypes.h)
description: The MPEG2_TRANSPORT_STRIDE structure describes the format block of the MPEG2 transport stride.
old-location: stream\mpeg2_transport_stride.htm
tech.root: stream
ms.assetid: 5756bb06-8fd3-4124-b3c8-35d5ed0bd57b
ms.date: 04/23/2018
keywords: ["_MPEG2_TRANSPORT_STRIDE structure"]
ms.keywords: "*PMPEG2_TRANSPORT_STRIDE, MPEG2_TRANSPORT_STRIDE, MPEG2_TRANSPORT_STRIDE structure [Streaming Media Devices], PMPEG2_TRANSPORT_STRIDE, PMPEG2_TRANSPORT_STRIDE structure pointer [Streaming Media Devices], _MPEG2_TRANSPORT_STRIDE, bdaref_66678748-2c73-4bb6-b4ba-fc1c28fe567b.xml, bdatypes/MPEG2_TRANSPORT_STRIDE, bdatypes/PMPEG2_TRANSPORT_STRIDE, stream.mpeg2_transport_stride"
f1_keywords:
 - "bdatypes/MPEG2_TRANSPORT_STRIDE"
req.header: bdatypes.h
req.include-header: Bdatypes.h
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
- HeaderDef
api_location:
- bdatypes.h
api_name:
- MPEG2_TRANSPORT_STRIDE
product:
- Windows
targetos: Windows
req.typenames: MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
---

# _MPEG2_TRANSPORT_STRIDE structure


## -description


The MPEG2_TRANSPORT_STRIDE structure describes the format block of the MPEG2 transport stride. 


## -struct-fields




### -field dwOffset

Offset in bytes into a packet.


### -field dwPacketLength

Size in bytes of a packet.


### -field dwStride

Stride of data in a packet. 


## -remarks



The MPEG2 transport stride format block is associated with the MEDIATYPE_Stream/MEDIASUBTYPE_MPEG2_TRANSPORT_STRIDE media type. Format blocks that are associated with this media type must start with the MPEG2_TRANSPORT_STRIDE structure.



