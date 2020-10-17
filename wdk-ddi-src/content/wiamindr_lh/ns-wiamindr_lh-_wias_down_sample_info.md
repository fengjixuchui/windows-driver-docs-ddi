---
UID: NS:wiamindr_lh._WIAS_DOWN_SAMPLE_INFO
title: _WIAS_DOWN_SAMPLE_INFO (wiamindr_lh.h)
description: The WIAS_DOWN_SAMPLE_INFO structure stores information used by the downsampling helper function, wiasDownSampleBuffer.
old-location: image\wias_down_sample_info.htm
tech.root: image
ms.assetid: af9d35d8-9e3c-4be0-8ba4-a0b548b1d7ac
ms.date: 05/03/2018
keywords: ["WIAS_DOWN_SAMPLE_INFO structure"]
ms.keywords: "*PWIAS_DOWN_SAMPLE_INFO, PWIAS_DOWN_SAMPLE_INFO, PWIAS_DOWN_SAMPLE_INFO structure pointer [Imaging Devices], WIAS_DOWN_SAMPLE_INFO, WIAS_DOWN_SAMPLE_INFO structure [Imaging Devices], _WIAS_DOWN_SAMPLE_INFO, image.wias_down_sample_info, wiamindr_lh/PWIAS_DOWN_SAMPLE_INFO, wiamindr_lh/WIAS_DOWN_SAMPLE_INFO, wiastrct_f7468047-47a4-4c3a-ada4-3bf329b32304.xml"
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
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
targetos: Windows
req.typenames: WIAS_DOWN_SAMPLE_INFO, *PWIAS_DOWN_SAMPLE_INFO
f1_keywords:
 - _WIAS_DOWN_SAMPLE_INFO
 - wiamindr_lh/_WIAS_DOWN_SAMPLE_INFO
 - PWIAS_DOWN_SAMPLE_INFO
 - wiamindr_lh/PWIAS_DOWN_SAMPLE_INFO
 - WIAS_DOWN_SAMPLE_INFO
 - wiamindr_lh/WIAS_DOWN_SAMPLE_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wiamindr_lh.h
api_name:
 - WIAS_DOWN_SAMPLE_INFO
---

# _WIAS_DOWN_SAMPLE_INFO structure


## -description

The WIAS_DOWN_SAMPLE_INFO structure stores information used by the downsampling helper function, [wiasDownSampleBuffer](../wiamdef/nf-wiamdef-wiasdownsamplebuffer.md).

## -struct-fields

### -field ulOriginalWidth

Specifies the width, in pixels, of the input data.

### -field ulOriginalHeight

Specifies the height, in pixels, of the input data.

### -field ulBitsPerPixel

Specifies the number of bits per pixel of the input data.

### -field ulXRes

Specifies the horizontal resolution of the input data.

### -field ulYRes

Specifies the vertical resolution of the input data.

### -field ulDownSampledWidth

Specifies the width, in pixels, of the output data.

### -field ulDownSampledHeight

Specifies the width, in pixels, of the output data.

### -field ulActualSize

Specifies the number of bytes placed in the destination buffer.

### -field ulDestBufSize

Specifies the size, in bytes, of the destination buffer.

### -field ulSrcBufSize

Specifies the size, in bytes, of the source buffer.

### -field pSrcBuffer

Points to the source buffer.

### -field pDestBuffer

Points to the destination buffer.

## -see-also

[wiasDownSampleBuffer](../wiamdef/nf-wiamdef-wiasdownsamplebuffer.md)