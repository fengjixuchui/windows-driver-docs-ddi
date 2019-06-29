---
UID: NS:d3dkmdt._DXGK_BRIGHTNESS_CAPS
title: _DXGK_BRIGHTNESS_CAPS (d3dkmdt.h)
description: Identifies brightness control capabilities of an integrated display panel that the display miniport driver provides through a call to its DxgkDdiGetBrightnessCaps function.
old-location: display\dxgk_brightness_caps.htm
tech.root: display
ms.assetid: e01ef4c9-1374-4d60-9307-32d878759c72
ms.date: 05/10/2018
ms.keywords: DXGK_BRIGHTNESS_CAPS, DXGK_BRIGHTNESS_CAPS structure [Display Devices], _DXGK_BRIGHTNESS_CAPS, d3dkmdt/DXGK_BRIGHTNESS_CAPS, display.dxgk_brightness_caps
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
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
- D3dkmdt.h
api_name:
- DXGK_BRIGHTNESS_CAPS
product:
- Windows
targetos: Windows
req.typenames: DXGK_BRIGHTNESS_CAPS
---

# _DXGK_BRIGHTNESS_CAPS structure


## -description


Identifies brightness control capabilities of an integrated display panel that the display miniport driver provides through a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgk_brightness_get_caps">DxgkDdiGetBrightnessCaps</a> function. Used by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers.


## -struct-fields




### -field SmoothBrightness

[in] If set, the integrated display panel supports smooth brightness control.

Setting this member is equivalent to setting the first bit of a 32-bit value (0x00000001).


### -field AdaptiveBrightness

[in] If set, the integrated display panel supports adaptive brightness control.

Setting this member is equivalent to setting the second bit of a 32-bit value (0x00000002).

### -field NitsBrightness

[in] Nit-based brightness support. If <b>NitsBrightness</b> is set, then the display brightness is calibrated to correspond to absolute brightness levels measured in nits.  Calibrated data provided to the Display Driver by OEMs should be taken with an On Pixel Ratio (OPR) percentage of 100% where each pixel is set to an RGB value of (255, 255, 255) or floating point equivalent.

If <b>NitsBrightness</b> is not set, then the OS will interpret all values that are defined in nits/millinits, for example [DXGK_BRIGHTNESS_NIT_RANGE](ns-d3dkmdt-_dxgk_brightness_nit_range.md), as uncalibrated thousandths of a percent of the maximum brightness level.

### -field Reserved

[in] This member is reserved and should be set to zero.
Setting this member is equivalent to setting the remaining 30 bits (0xFFFFFFFC) of a 32-bit value to zeros.


### -field Value

[in] A member in the union that <b>DXGK_BRIGHTNESS_CAPS</b> contains that can hold one 32-bit value that identifies information about the display miniport driver's brightness control capabilities.


## -remarks



Do not assume that the <b>SmoothBrightness</b> members of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_dxgk_brightness_state">DXGK_BRIGHTNESS_STATE</a> and <b>DXGK_BRIGHTNESS_CAPS</b> are the same. <b>DXGK_BRIGHTNESS_STATE</b>.<b>SmoothBrightness</b> is used to enable  smooth brightness control on an integrated display panel. <b>DXGK_BRIGHTNESS_CAPS</b>.<b>SmoothBrightness</b> is used to query smooth brightness control capabilities of the integrated display panel.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_dxgk_brightness_state">DXGK_BRIGHTNESS_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgk_brightness_get_caps">DxgkDdiGetBrightnessCaps</a>
 

 

