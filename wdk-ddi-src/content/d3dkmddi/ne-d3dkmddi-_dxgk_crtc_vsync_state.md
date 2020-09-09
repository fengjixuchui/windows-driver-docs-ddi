---
UID: NE:d3dkmddi._DXGK_CRTC_VSYNC_STATE
title: _DXGK_CRTC_VSYNC_STATE (d3dkmddi.h)
description: Provides additional information for DxgkDdi_ControlInterrupt2 when VSYNC is being utilized.
old-location: display\dxgk_crtc_vsync_state.htm
ms.assetid: 1A7632BB-1DA6-4D03-8A3A-6468A2E4DF71
ms.date: 05/10/2018
keywords: ["DXGK_CRTC_VSYNC_STATE enumeration"]
ms.keywords: DXGK_CRTC_VSYNC_STATE, DXGK_CRTC_VSYNC_STATE enumeration [Display Devices], DXGK_INTERRUPT_ENABLE, DXGK_VSYNC_DISABLE_KEEP_PHASE, DXGK_VSYNC_DISABLE_NO_PHASE, _DXGK_CRTC_VSYNC_STATE, d3dkmddi/DXGK_CRTC_VSYNC_STATE, d3dkmddi/DXGK_INTERRUPT_ENABLE, d3dkmddi/DXGK_VSYNC_DISABLE_KEEP_PHASE, d3dkmddi/DXGK_VSYNC_DISABLE_NO_PHASE, display.dxgk_crtc_vsync_state
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10.
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
tech.root: display
req.typenames: DXGK_CRTC_VSYNC_STATE
f1_keywords:
 - _DXGK_CRTC_VSYNC_STATE
 - d3dkmddi/_DXGK_CRTC_VSYNC_STATE
 - DXGK_CRTC_VSYNC_STATE
 - d3dkmddi/DXGK_CRTC_VSYNC_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGK_CRTC_VSYNC_STATE
---

# _DXGK_CRTC_VSYNC_STATE enumeration


## -description

Provides additional information for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_controlinterrupt2">DxgkDdi_ControlInterrupt2 </a>when VSYNC is being utilized.

## -enum-fields

### -field DXGK_VSYNC_ENABLE

Indicates that the VSYNC interrupt is enabled and will call into the interrupt callback whenever a display target enters the VBLANK state.

### -field DXGK_VSYNC_DISABLE_KEEP_PHASE

Indicates that the VSYNC interrupt is disabled and the display driver will ensure that any request to re-enter the VSYNC enabled state will do so in the phase of interrupts prior to disable.

### -field DXGK_VSYNC_DISABLE_NO_PHASE

Indicates that the VSYNC interrupt is disabled, but that the display driver will not require re-entering the VSYNC enabled state in phase of prior interrupts.

