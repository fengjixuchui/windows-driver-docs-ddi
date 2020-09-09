---
UID: NS:dxva._DXVA_VideoSample
title: _DXVA_VideoSample (dxva.h)
description: The DXVA_VideoSample structure is sent by the renderer to the driver to specify the format of a video sample.
old-location: display\dxva_videosample.htm
tech.root: display
ms.assetid: 2fab4993-0b34-44ce-a905-5094e6e3ce47
ms.date: 05/10/2018
keywords: ["DXVA_VideoSample structure"]
ms.keywords: "*LPDXVA_VideoSample, DXVA_VideoSample, DXVA_VideoSample structure [Display Devices], LPDXVA_VideoSample, LPDXVA_VideoSample structure pointer [Display Devices], _DXVA_VideoSample, display.dxva_videosample, dxva/DXVA_VideoSample, dxva/LPDXVA_VideoSample, dxvaref_08c56205-0793-4556-bb9a-e682eb6ca354.xml"
req.header: dxva.h
req.include-header: Dxva.h
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
req.typenames: DXVA_VideoSample, *LPDXVA_VideoSample
f1_keywords:
 - _DXVA_VideoSample
 - dxva/_DXVA_VideoSample
 - LPDXVA_VideoSample
 - dxva/LPDXVA_VideoSample
 - DXVA_VideoSample
 - dxva/DXVA_VideoSample
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dxva.h
api_name:
 - DXVA_VideoSample
---

# _DXVA_VideoSample structure


## -description

The DXVA_VideoSample structure is sent by the renderer to the driver to specify the format of a video sample.

## -struct-fields

### -field rtStart

Specifies the start time of the sample.

### -field rtEnd

Specifies the end time of the sample.

### -field SampleFormat

Specifies the format of the sample as defined by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_sampleformat">DXVA_SampleFormat</a> structure.

### -field lpDDSSrcSurface

Pointer to a <a href="https://docs.microsoft.com/windows/win32/api/ddrawint/ns-ddrawint-dd_surface_local">DD_SURFACE_LOCAL</a> structure.

## -see-also

<a href="https://docs.microsoft.com/windows/win32/api/ddrawint/ns-ddrawint-dd_surface_local">DD_SURFACE_LOCAL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_deinterlaceblt">DXVA_DeinterlaceBlt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ne-dxva-_dxva_sampleformat">DXVA_SampleFormat</a>

