---
UID: NS:d3d12umddi.D3D12DDI_TEXTURE_LAYOUT_CAPS_0026
title: D3D12DDI_TEXTURE_LAYOUT_CAPS_0026 (d3d12umddi.h)
description: Specifies texture layout capabilities.
old-location: display\d3d12ddi_texture_layout_caps_0026.htm
ms.assetid: A64D2A22-5702-4931-AF2F-58BB919D764E
ms.date: 05/10/2018
ms.keywords: D3D12DDI_TEXTURE_LAYOUT_CAPS_0026, D3D12DDI_TEXTURE_LAYOUT_CAPS_0026 structure [Display Devices], d3d12umddi/D3D12DDI_TEXTURE_LAYOUT_CAPS_0026, display.d3d12ddi_texture_layout_caps_0026
ms.topic: struct
f1_keywords:
 - "d3d12umddi/D3D12DDI_TEXTURE_LAYOUT_CAPS_0026"
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d12umddi.h
api_name:
- D3D12DDI_TEXTURE_LAYOUT_CAPS_0026
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_TEXTURE_LAYOUT_CAPS_0026
---

# D3D12DDI_TEXTURE_LAYOUT_CAPS_0026 structure


## -description


Specifies texture layout capabilities.


## -struct-fields




### -field DeviceDependentLayoutCount

A device dependent layout count. This must be the number of device-dependent layouts supported by the adapter. 


### -field DeviceDependentSwizzleCount

A device dependent swizzle count. This must be the number of device-dependent swizzle patterns supported by the adapter. 


### -field Supports64KStandardSwizzle

Whether the texture layout supports 64K standard swizzle.


### -field SupportsRowMajorTexture

Whether the texture layout supports row major texture.


### -field IndexableSwizzlePatterns

Whether the texture layout can choose any swizzle pattern for a subresource. 

