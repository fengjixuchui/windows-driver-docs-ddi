---
UID: NS:d3dkmthk._D3DKMT_DMM_ESCAPE
title: _D3DKMT_DMM_ESCAPE (d3dkmthk.h)
description: Do not use the D3DKMT_DMM_ESCAPE structure; it is for testing purposes only. The D3DKMT_DMM_ESCAPE structure describes how to control the display mode manager (DMM) in a call to the D3DKMTEscape function.
old-location: display\d3dkmt_dmm_escape.htm
ms.assetid: 9d4a317d-bb0c-47d4-b9f2-e668adc4d0d4
ms.date: 05/10/2018
keywords: ["D3DKMT_DMM_ESCAPE structure"]
ms.keywords: D3DKMT_DMM_ESCAPE, D3DKMT_DMM_ESCAPE structure [Display Devices], OpenGL_Structs_670cf3b6-6c85-4ddc-af88-8891e3f8f6ce.xml, _D3DKMT_DMM_ESCAPE, d3dkmthk/D3DKMT_DMM_ESCAPE, display.d3dkmt_dmm_escape
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
targetos: Windows
tech.root: display
req.typenames: D3DKMT_DMM_ESCAPE
f1_keywords:
 - _D3DKMT_DMM_ESCAPE
 - d3dkmthk/_D3DKMT_DMM_ESCAPE
 - D3DKMT_DMM_ESCAPE
 - d3dkmthk/D3DKMT_DMM_ESCAPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMT_DMM_ESCAPE
---

# _D3DKMT_DMM_ESCAPE structure


## -description

   Do not use the D3DKMT_DMM_ESCAPE structure; it is for testing purposes only.
   

The D3DKMT_DMM_ESCAPE structure describes how to control the display mode manager (DMM) in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtescape">D3DKMTEscape</a> function.

## -struct-fields

### -field Type

### -field ProvidedBufferSize

actual size of Data[] array, in bytes.

### -field MinRequiredBufferSize

minimum required size of Data[] array to contain requested data.

### -field Data

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtescape">D3DKMTEscape</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_escape">D3DKMT_ESCAPE</a>

