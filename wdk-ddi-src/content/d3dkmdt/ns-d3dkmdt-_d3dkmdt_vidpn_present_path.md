---
UID: NS:d3dkmdt._D3DKMDT_VIDPN_PRESENT_PATH
title: _D3DKMDT_VIDPN_PRESENT_PATH (d3dkmdt.h)
description: The D3DKMDT_VIDPN_PRESENT_PATH structure contains information about a video present path.
old-location: display\d3dkmdt_vidpn_present_path.htm
tech.root: display
ms.assetid: 3676476d-babe-4d68-995b-b7068a587bbc
ms.date: 05/10/2018
keywords: ["_D3DKMDT_VIDPN_PRESENT_PATH structure"]
ms.keywords: D3DKMDT_VIDPN_PRESENT_PATH, D3DKMDT_VIDPN_PRESENT_PATH structure [Display Devices], DmStructs_7cf350db-f1fa-492f-96d2-9ad806f2b75a.xml, _D3DKMDT_VIDPN_PRESENT_PATH, d3dkmdt/D3DKMDT_VIDPN_PRESENT_PATH, display.d3dkmdt_vidpn_present_path
f1_keywords:
 - "d3dkmdt/D3DKMDT_VIDPN_PRESENT_PATH"
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
- d3dkmdt.h
api_name:
- D3DKMDT_VIDPN_PRESENT_PATH
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_VIDPN_PRESENT_PATH
---

# _D3DKMDT_VIDPN_PRESENT_PATH structure


## -description


The D3DKMDT_VIDPN_PRESENT_PATH structure contains information about a video present path.


## -struct-fields




### -field VidPnSourceId

The identifier of the path's video present source.


### -field VidPnTargetId

The identifier of the path's video present target.


### -field ImportanceOrdinal

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_vidpn_present_path_importance">D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE</a> enumerator that specifies the importance of the path relative to other paths. For example, the path presenting the primary view might have higher importance than other paths so that it will be assigned the best source and target mode sets. Path importance ordinal numbers are unique within a given video present network (VidPN) topology. 


### -field ContentTransformation

 A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path_transformation">D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION</a> enumerator that indicates the transformation applied to the content presented on the video present path.


### -field VisibleFromActiveTLOffset

A D3DKMDT_2DOFFSET structure that contains the offset, in pixels, from the top-left corner of the video signal's active pixels to the top-left corner of the monitor's visible pixels. The D3DKMDT_2DOFFSET data type is defined in <i>D3dkmdt.h</i> as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_2dregion">D3DKMDT_2DREGION</a> structure.


### -field VisibleFromActiveBROffset

A D3DKMDT_2DOFFSET structure that contains the offset, in pixels, from the lower-right corner of the video signal's active pixels to the lower-right corner of the monitor's visible pixels.


### -field VidPnTargetColorBasis

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_color_basis">D3DKMDT_COLOR_BASIS</a> enumerator that specifies the color basis used by the path's video present target.


### -field VidPnTargetColorCoeffDynamicRanges

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_color_coeff_dynamic_ranges">D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES</a> structure that specifies a range for each channel in the color basis used by the path's video present target.


### -field Content

A value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_vidpn_present_path_content">D3DKMDT_VIDPN_PRESENT_PATH_CONTENT</a> enumeration that indicates the type of content, graphics or video, displayed by the path.


### -field CopyProtection

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path_copyprotection">D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION</a> structure that describes the copy protection supported by, and currently active on, the path.


### -field GammaRamp

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_gamma_ramp">D3DKMDT_GAMMA_RAMP</a> structure that contains a description of a gamma lookup table and a pointer to the lookup table.


## -remarks



A video present path represents a connection between a video present source (view) and a video present target (output) on a display adapter. For more information about video present networks, paths, sources, and targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/introduction-to-video-present-networks">Introduction to Video Present Networks</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_updateactivevidpnpresentpath">DxgkDdiUpdateActiveVidPnPresentPath</a>
 

 

