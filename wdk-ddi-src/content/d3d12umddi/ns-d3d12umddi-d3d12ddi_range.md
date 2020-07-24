---
UID: NS:d3d12umddi.D3D12DDI_RANGE
title: D3D12DDI_RANGE (d3d12umddi.h)
description: Specifies a range.
old-location: display\d3d12ddi_range.htm
ms.assetid: B3A8F252-D56D-4F20-A0DE-2A29904BC907
ms.date: 05/10/2018
keywords: ["D3D12DDI_RANGE structure"]
ms.keywords: D3D12DDI_RANGE, D3D12DDI_RANGE structure [Display Devices], d3d12umddi/D3D12DDI_RANGE, display.d3d12ddi_range
f1_keywords:
 - "d3d12umddi/D3D12DDI_RANGE"
 - "D3D12DDI_RANGE"
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
- D3D12DDI_RANGE
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_RANGE
---

# D3D12DDI_RANGE structure


## -description


Specifies a range.


## -struct-fields




### -field Begin

The beginning of the range.


### -field End

A value of one more than the end of the range. Therefore, the value of <i>End</i> minus the value of <i>Begin</i> is the size of the range.

