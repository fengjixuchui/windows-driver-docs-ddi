---
UID: NS:d3dhal._D3DHAL_DP2CREATELIGHT
title: _D3DHAL_DP2CREATELIGHT (d3dhal.h)
description: The D3DHAL_DP2CREATELIGHT structure is used to create a light for D3dDrawPrimitives2.
old-location: display\d3dhal_dp2createlight.htm
tech.root: display
ms.assetid: 26dc353a-13e0-4408-b30f-4a9086cd7b9a
ms.date: 05/10/2018
keywords: ["_D3DHAL_DP2CREATELIGHT structure"]
ms.keywords: "*LPD3DHAL_DP2CREATELIGHT, D3DHAL_DP2CREATELIGHT, D3DHAL_DP2CREATELIGHT structure [Display Devices], LPD3DHAL_DP2CREATELIGHT, LPD3DHAL_DP2CREATELIGHT structure pointer [Display Devices], _D3DHAL_DP2CREATELIGHT, d3dhal/D3DHAL_DP2CREATELIGHT, d3dhal/LPD3DHAL_DP2CREATELIGHT, d3dstrct_8cbc2e0d-9728-407d-a860-b9460b33e837.xml, display.d3dhal_dp2createlight"
f1_keywords:
 - "d3dhal/D3DHAL_DP2CREATELIGHT"
req.header: d3dhal.h
req.include-header: D3dhal.h
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
- d3dhal.h
api_name:
- D3DHAL_DP2CREATELIGHT
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2CREATELIGHT
---

# _D3DHAL_DP2CREATELIGHT structure


## -description


The D3DHAL_DP2CREATELIGHT structure is used to create a light for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>.


## -struct-fields




### -field dwIndex

Specifies the index of the light being created.


## -remarks



The D3DHAL_DP2CREATELIGHT structure is used to hold the index into the light array. The driver should enlarge its light array as necessary to accommodate at least as many lights as specified by the index.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>
 

 

