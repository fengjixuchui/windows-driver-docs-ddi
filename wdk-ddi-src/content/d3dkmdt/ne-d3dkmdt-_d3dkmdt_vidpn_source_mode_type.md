---
UID: NE:d3dkmdt._D3DKMDT_VIDPN_SOURCE_MODE_TYPE
title: _D3DKMDT_VIDPN_SOURCE_MODE_TYPE (d3dkmdt.h)
description: The D3DKMDT_VIDPN_SOURCE_MODE_TYPE enumeration is used to indicate whether a video present network (VidPN) source mode is a graphics mode, a text mode, or a stereo mode.
old-location: display\d3dkmdt_vidpn_source_mode_type.htm
tech.root: display
ms.assetid: c2a48cf2-f595-4f78-b779-416d324e90d7
ms.date: 05/10/2018
keywords: ["_D3DKMDT_VIDPN_SOURCE_MODE_TYPE enumeration"]
ms.keywords: D3DKMDT_RMT_GRAPHICS, D3DKMDT_RMT_GRAPHICS_STEREO, D3DKMDT_RMT_GRAPHICS_STEREO_ADVANCED_SCAN, D3DKMDT_RMT_TEXT, D3DKMDT_RMT_UNINITIALIZED, D3DKMDT_VIDPN_SOURCE_MODE_TYPE, D3DKMDT_VIDPN_SOURCE_MODE_TYPE enumeration [Display Devices], DmEnums_602e0ab4-4fea-489f-8f2e-c8cf9534caa8.xml, _D3DKMDT_VIDPN_SOURCE_MODE_TYPE, d3dkmdt/D3DKMDT_RMT_GRAPHICS, d3dkmdt/D3DKMDT_RMT_GRAPHICS_STEREO, d3dkmdt/D3DKMDT_RMT_GRAPHICS_STEREO_ADVANCED_SCAN, d3dkmdt/D3DKMDT_RMT_TEXT, d3dkmdt/D3DKMDT_RMT_UNINITIALIZED, d3dkmdt/D3DKMDT_VIDPN_SOURCE_MODE_TYPE, display.d3dkmdt_vidpn_source_mode_type
f1_keywords:
 - "d3dkmdt/D3DKMDT_VIDPN_SOURCE_MODE_TYPE"
 - "D3DKMDT_VIDPN_SOURCE_MODE_TYPE"
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
- D3DKMDT_VIDPN_SOURCE_MODE_TYPE
targetos: Windows
req.typenames: D3DKMDT_VIDPN_SOURCE_MODE_TYPE
---

# _D3DKMDT_VIDPN_SOURCE_MODE_TYPE enumeration


## -description


The D3DKMDT_VIDPN_SOURCE_MODE_TYPE enumeration is used to indicate whether a video present network (VidPN) source mode is a graphics mode, a text mode, or a stereo mode.


## -enum-fields




### -field D3DKMDT_RMT_UNINITIALIZED

Indicates that a variable of type D3DKMDT_VIDPN_SOURCE_MODE_TYPE has not yet been assigned a meaningful value.


### -field D3DKMDT_RMT_GRAPHICS

Indicates that the VidPN source mode is a graphics mode.


### -field D3DKMDT_RMT_TEXT

Indicates that the VidPN source mode is a text mode.


### -field D3DKMDT_RMT_GRAPHICS_STEREO

Available beginning with Windows 8.

Indicates that the VidPN source mode is stereo, and the allocation can only be scanned by the display miniport driver as both left and right channels.


### -field D3DKMDT_RMT_GRAPHICS_STEREO_ADVANCED_SCAN

Available beginning with Windows 8.

Indicates that the VidPN source mode is stereo, and the allocation can only be scanned by the display miniport driver as both left and right channels, or as only the left channel, or as only  the right channel.

If mono content needs to be displayed in a stereo mode, the operating system can better manage resources if <b>D3DKMDT_RMT_GRAPHICS_STEREO_ADVANCED_SCAN</b> is set instead of <b>D3DKMDT_RMT_GRAPHICS_STEREO</b>.


## -remarks



The <b>Type</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_source_mode">D3DKMDT_VIDPN_SOURCE_MODE</a> structure is a D3DKMDT_VIDPN_SOURCE_MODE_TYPE value.



