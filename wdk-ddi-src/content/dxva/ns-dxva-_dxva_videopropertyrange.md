---
UID: NS:dxva._DXVA_VideoPropertyRange
title: _DXVA_VideoPropertyRange (dxva.h)
description: The DXVA_VideoPropertyRange structure specifies the range of allowed values for ProcAmp control properties.
old-location: display\dxva_videopropertyrange.htm
tech.root: display
ms.assetid: e78fa9ba-7573-47db-b4d8-9b7584d5b432
ms.date: 05/10/2018
keywords: ["DXVA_VideoPropertyRange structure"]
ms.keywords: "*LPDXVA_VideoPropertyRange, DXVA_VideoPropertyRange, DXVA_VideoPropertyRange structure [Display Devices], LPDXVA_VideoPropertyRange, LPDXVA_VideoPropertyRange structure pointer [Display Devices], _DXVA_VideoPropertyRange, display.dxva_videopropertyrange, dxva/DXVA_VideoPropertyRange, dxva/LPDXVA_VideoPropertyRange, dxvaref_0e7bc2aa-0404-4025-908a-5d4c528e020b.xml"
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: DirectX 9.0 and later versions only.
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
req.typenames: DXVA_VideoPropertyRange, *LPDXVA_VideoPropertyRange
f1_keywords:
 - _DXVA_VideoPropertyRange
 - dxva/_DXVA_VideoPropertyRange
 - LPDXVA_VideoPropertyRange
 - dxva/LPDXVA_VideoPropertyRange
 - DXVA_VideoPropertyRange
 - dxva/DXVA_VideoPropertyRange
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dxva.h
api_name:
 - DXVA_VideoPropertyRange
---

# _DXVA_VideoPropertyRange structure


## -description

The DXVA_VideoPropertyRange structure specifies the range of allowed values for ProcAmp control properties.

## -struct-fields

### -field MinValue

Specifies the minimum value allowed for a given property.

### -field MaxValue

Specifies the maximum value allowed for a given property.

### -field DefaultValue

Specifies the default value for a given property.

### -field StepSize

Specifies the step size increment for a given property.

## -see-also

<a href="/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_videodesc">DXVA_VideoDesc</a>