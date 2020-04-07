---
UID: NE:netdispumdddi.__unnamed_enum_3
title: MIRACAST_CHUNK_TYPE (netdispumdddi.h)
description: Specifies the types of wireless display (Miracast) chunk info that is to be processed.
old-location: display\miracast_chunk_type.htm
tech.root: display
ms.assetid: 39911172-f916-4ca2-8d98-9d53fbc30807
ms.date: 05/10/2018
keywords: ["MIRACAST_CHUNK_TYPE enumeration"]
ms.keywords: MIRACAST_CHUNK_TYPE, MIRACAST_CHUNK_TYPE enumeration [Display Devices], MIRACAST_CHUNK_TYPE_COLOR_CONVERT_COMPLETE, MIRACAST_CHUNK_TYPE_ENCODE_COMPLETE, MIRACAST_CHUNK_TYPE_ENCODE_DRIVER_DEFINED_1, MIRACAST_CHUNK_TYPE_ENCODE_DRIVER_DEFINED_2, MIRACAST_CHUNK_TYPE_ENCODE_FORCE_UINT32, MIRACAST_CHUNK_TYPE_FRAME_DROPPED, MIRACAST_CHUNK_TYPE_FRAME_START, MIRACAST_CHUNK_TYPE_UNKNOWN, display.miracast_chunk_type, netdispumdddi/MIRACAST_CHUNK_TYPE, netdispumdddi/MIRACAST_CHUNK_TYPE_COLOR_CONVERT_COMPLETE, netdispumdddi/MIRACAST_CHUNK_TYPE_ENCODE_COMPLETE, netdispumdddi/MIRACAST_CHUNK_TYPE_ENCODE_DRIVER_DEFINED_1, netdispumdddi/MIRACAST_CHUNK_TYPE_ENCODE_DRIVER_DEFINED_2, netdispumdddi/MIRACAST_CHUNK_TYPE_ENCODE_FORCE_UINT32, netdispumdddi/MIRACAST_CHUNK_TYPE_FRAME_DROPPED, netdispumdddi/MIRACAST_CHUNK_TYPE_FRAME_START, netdispumdddi/MIRACAST_CHUNK_TYPE_UNKNOWN
f1_keywords:
 - "netdispumdddi/MIRACAST_CHUNK_TYPE"
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
- Netdispumdddi.h
api_name:
- MIRACAST_CHUNK_TYPE
product:
- Windows
targetos: Windows
req.typenames: MIRACAST_CHUNK_TYPE
---

# MIRACAST_CHUNK_TYPE enumeration


## -description


Specifies the types of wireless display (Miracast) chunk info that is to be processed.


## -enum-fields




### -field MIRACAST_CHUNK_TYPE_UNKNOWN

An unknown or undefined chunk type.


### -field MIRACAST_CHUNK_TYPE_COLOR_CONVERT_COMPLETE

Color conversion has completed on the chunk.


### -field MIRACAST_CHUNK_TYPE_ENCODE_COMPLETE

Encoding has completed on the chunk.


### -field MIRACAST_CHUNK_TYPE_FRAME_START

The chunk is at the start of the Wi-Fi frame.


### -field MIRACAST_CHUNK_TYPE_FRAME_DROPPED

The chunk is in a dropped Wi-Fi frame.


### -field MIRACAST_CHUNK_TYPE_ENCODE_DRIVER_DEFINED_1

Encoding is driver-defined, of type 1.


### -field MIRACAST_CHUNK_TYPE_ENCODE_DRIVER_DEFINED_2

Encoding is driver-defined, of type 2.


### -field MIRACAST_CHUNK_TYPE_ENCODE_FORCE_UINT32

Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. You should not use this value.

