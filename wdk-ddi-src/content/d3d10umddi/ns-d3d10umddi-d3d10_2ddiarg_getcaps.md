---
UID: NS:d3d10umddi.D3D10_2DDIARG_GETCAPS
title: D3D10_2DDIARG_GETCAPS (d3d10umddi.h)
description: The D3D10_2DDIARG_GETCAPS structure contains display device capabilities of a particular type.
old-location: display\d3d10_2ddiarg_getcaps.htm
ms.assetid: 3a22464f-4e0b-4b14-bdbf-b34b3abf9780
ms.date: 05/10/2018
keywords: ["D3D10_2DDIARG_GETCAPS structure"]
ms.keywords: D3D10_2DDIARG_GETCAPS, D3D10_2DDIARG_GETCAPS structure [Display Devices], UMDisplayDriver_Dx11param_Structs_0d9c80db-e29f-4e2f-b697-bcf87f29034c.xml, d3d10umddi/D3D10_2DDIARG_GETCAPS, display.d3d10_2ddiarg_getcaps
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D10_2DDIARG_GETCAPS is supported beginning with the Windows 7 operating system.
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
req.typenames: D3D10_2DDIARG_GETCAPS
f1_keywords:
 - D3D10_2DDIARG_GETCAPS
 - d3d10umddi/D3D10_2DDIARG_GETCAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D10_2DDIARG_GETCAPS
---

# D3D10_2DDIARG_GETCAPS structure


## -description

The D3D10_2DDIARG_GETCAPS structure contains display device capabilities of a particular type.

## -struct-fields

### -field Type

[in] The type of capabilities to retrieve. The Microsoft Direct3D runtime can supply one of the values from the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_2ddicaps_type">D3D10_2DDICAPS_TYPE</a> enumeration, possibly along with information in the memory block that is pointed to by <b>pInfo</b>, to retrieve particular capability data in the memory block at <b>pData</b>.

### -field pInfo

[in] A pointer to a memory block that contains data that specifies the specific condition on which to retrieve the capabilities of the type that is specified by the <b>Type</b> member.

### -field pData

[out] A pointer to a memory block that is filled with capabilities of the type that is specified by the <b>Type</b> member and possibly determined by the condition that is specified in the memory block at <b>pInfo</b>.

### -field DataSize

[in/out] The size, in bytes, of the memory block at <b>pData</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_2ddicaps_type">D3D10_2DDICAPS_TYPE</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getcaps">GetCaps(D3D10_2)</a>