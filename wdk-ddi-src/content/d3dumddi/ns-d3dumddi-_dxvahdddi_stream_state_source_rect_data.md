---
UID: NS:d3dumddi._DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA
title: _DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA (d3dumddi.h)
description: The DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA structure describes stream-state data that specifies the source rectangle of the input stream.
old-location: display\dxvahdddi_stream_state_source_rect_data.htm
tech.root: display
ms.assetid: 2ce67fd7-03f6-432c-9229-a99f66f7eb73
ms.date: 05/10/2018
keywords: ["DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA structure"]
ms.keywords: DXVA2_Structs_82045602-8c6c-4a80-8698-06b34f0ca8d9.xml, DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA, DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA structure [Display Devices], _DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA, d3dumddi/DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA, display.dxvahdddi_stream_state_source_rect_data
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA is supported beginning with the Windows 7 operating system.
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
req.typenames: DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA
f1_keywords:
 - _DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA
 - d3dumddi/_DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA
 - DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA
 - d3dumddi/DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA
---

# _DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA structure


## -description

The DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA structure describes stream-state data that specifies the source rectangle of the input stream. The driver scales the source rectangle within the input surface to the destination rectangle within the output surface.

## -struct-fields

### -field Enable

[in] A Boolean value that specifies whether the driver should use the <b>SourceRect</b> member or the entire input surface as the source. The default value is <b>FALSE</b>, which indicates that the entire input surface is the source.

### -field SourceRect

[in] A <a href="/windows/win32/api/windef/ns-windef-rect">RECT</a> structure that specifies the source rectangle in the coordinates of the input surface. This member is relevant only when the <b>Enable</b> member is set to <b>TRUE</b>. The default value is (0,0,0,0).

## -remarks

If the <b>Enable</b> member is set to <b>TRUE</b> and the source rectangle that the <b>SourceRect</b> member specifies is not within the input surface, the intersection of the source rectangle and the input surface is used as the source rectangle. 

The application can use the source rectangle to specify the active rectangle (dirty region) of the source surface.

## -see-also

<a href="/windows/win32/api/windef/ns-windef-rect">RECT</a>