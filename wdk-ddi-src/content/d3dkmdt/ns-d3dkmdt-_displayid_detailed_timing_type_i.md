---
UID: NS:d3dkmdt._DISPLAYID_DETAILED_TIMING_TYPE_I
title: _DISPLAYID_DETAILED_TIMING_TYPE_I (d3dkmdt.h)
description: The DISPLAYID_DETAILED_TIMING_TYPE_I structure specifies an additional target mode set for a video present target.
old-location: display\displayid_detailed_timing_type_i.htm
tech.root: display
ms.assetid: 7b3fa3a4-a77a-4c5f-b157-1fbdc3a7be33
ms.date: 05/10/2018
keywords: ["DISPLAYID_DETAILED_TIMING_TYPE_I structure"]
ms.keywords: DISPLAYID_DETAILED_TIMING_TYPE_I, DISPLAYID_DETAILED_TIMING_TYPE_I structure [Display Devices], DmStructs_75d5fd93-c7ae-4a57-9843-427c53a9416f.xml, _DISPLAYID_DETAILED_TIMING_TYPE_I, d3dkmdt/DISPLAYID_DETAILED_TIMING_TYPE_I, display.displayid_detailed_timing_type_i
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
req.typenames: DISPLAYID_DETAILED_TIMING_TYPE_I
f1_keywords:
 - _DISPLAYID_DETAILED_TIMING_TYPE_I
 - d3dkmdt/_DISPLAYID_DETAILED_TIMING_TYPE_I
 - DISPLAYID_DETAILED_TIMING_TYPE_I
 - d3dkmdt/DISPLAYID_DETAILED_TIMING_TYPE_I
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - DISPLAYID_DETAILED_TIMING_TYPE_I
---

# _DISPLAYID_DETAILED_TIMING_TYPE_I structure


## -description

The DISPLAYID_DETAILED_TIMING_TYPE_I structure specifies an additional target mode set for a video present target.

## -struct-fields

### -field PixelClock

[in] The display pixel clock rate, in units of 10 KHz. Clock rate must be between 1 MHz and 10 GHz, inclusive.

### -field AspectRatio

[in] The display aspect ratio, which must be one of the values in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_displayid_detailed_timing_type_i_aspect_ratio">DISPLAYID_DETAILED_TIMING_TYPE_I_ASPECT_RATIO</a> enumeration.

### -field Reserved

[in] Reserved for system use.

### -field ScanningType

[in] The frame scanning type. Must be one of the values in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_displayid_detailed_timing_type_i_scanning_mode">DISPLAYID_DETAILED_TIMING_TYPE_I_SCANNING_MODE</a> enumeration.

### -field StereoMode

[in] The display stereo vision mode. Must be one of the values in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_displayid_detailed_timing_type_i_stereo_mode">DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE</a> enumeration.

### -field PreferredTiming

       [in] Indicates whether the first 128-byte block of a monitor's Extended Display Identification Data <a href="https://docs.microsoft.com/windows-hardware/drivers/">Extended Display Identification Data (EDID)</a> contains detailed timing data. This must be 1 if the display conforms to EDID version 1.3 and later.

### -field HorizontalActivePixels

[in] The number of active pixels in the horizontal direction.

### -field HorizontalBlankPixels

[in] The number of blank pixels in the horizontal direction.

### -field HorizontalFrontPorch

[in] The horizontal front porch interval, in pixels. The front porch is the blanking interval before the sync pulse.

### -field HorizontalSyncPolarity

[in] The horizontal sync polarity, which must be one of the values in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_displayid_detailed_timing_type_i_sync_polarity">DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY</a> enumeration.

### -field HorizontalSyncWidth

[in] The horizontal sync interval, in pixels.

### -field VerticalActiveLines

[in] The number of active scan lines.

### -field VerticalBlankLines

[in] The number of blank scan lines.

### -field VerticalFrontPorch

[in] The vertical front porch interval, in number of lines. The front porch is the blanking interval before the sync pulse.

### -field VerticalSyncPolarity

[in] The vertical sync polarity. Must be one of the values in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_displayid_detailed_timing_type_i_sync_polarity">DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY</a> enumeration.

### -field VerticalSyncWidth

[in] The vertical sync interval, in number of lines.

## -remarks

The Microsoft DirectX graphics kernel subsystem fills this structure by reading the additional target mode data that is stored in the registry at the following path:

<b>HKEY_LOCAL_MACHINE\ SYSTEM\ CurrentControlSet\ Control\ GraphicsDrivers\ AdditionalTargetModeLists</b>

The graphics kernel subsystem also validates that each registry value meets the requirements described above for each respective member.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_displayid_detailed_timing_type_i_aspect_ratio">DISPLAYID_DETAILED_TIMING_TYPE_I_ASPECT_RATIO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_displayid_detailed_timing_type_i_scanning_mode">DISPLAYID_DETAILED_TIMING_TYPE_I_SCANNING_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_displayid_detailed_timing_type_i_stereo_mode">DISPLAYID_DETAILED_TIMING_TYPE_I_STEREO_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_displayid_detailed_timing_type_i_sync_polarity">DISPLAYID_DETAILED_TIMING_TYPE_I_SYNC_POLARITY</a>

