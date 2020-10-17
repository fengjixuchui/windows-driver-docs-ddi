---
UID: NS:d3dumddi._D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE
title: _D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE (d3dumddi.h)
description: The D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE structure describes the private bit-block transfer (bitblt) state of the video processor to retrieve.
old-location: display\d3dddiarg_dxvahd_getvideoprocessbltstateprivate.htm
tech.root: display
ms.assetid: 0b6c0033-d6aa-4662-8818-ea737cf5a1c0
ms.date: 05/10/2018
keywords: ["D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE structure"]
ms.keywords: D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE, D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE structure [Display Devices], UMDisplayDriver_param_Structs_998b4bf8-b2ff-48a4-b4d4-1d41ecd08558.xml, _D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE, d3dumddi/D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE, display.d3dddiarg_dxvahd_getvideoprocessbltstateprivate
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE is supported beginning with the Windows 7 operating system.
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
req.typenames: D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE
f1_keywords:
 - _D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE
 - d3dumddi/_D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE
 - D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE
 - d3dumddi/D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE
---

# _D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE structure


## -description

The D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE structure describes the private bit-block transfer (bitblt) state of the video processor to retrieve.

## -struct-fields

### -field hVideoProcessor

[in] A handle to the video processor whose private bitblt state the runtime requests.

### -field pData

[in/out] A pointer to <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_blt_state_private_data">DXVAHDDDI_BLT_STATE_PRIVATE_DATA</a> structure that identifies the private bitblt state to retrieve. The driver uses DXVAHDDDI_BLT_STATE_PRIVATE_DATA to return the private bitblt data.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_blt_state_private_data">DXVAHDDDI_BLT_STATE_PRIVATE_DATA</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_getvideoprocessbltstateprivate">GetVideoProcessBltStatePrivate</a>