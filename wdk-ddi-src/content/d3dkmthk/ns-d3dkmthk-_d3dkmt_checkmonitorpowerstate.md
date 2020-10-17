---
UID: NS:d3dkmthk._D3DKMT_CHECKMONITORPOWERSTATE
title: _D3DKMT_CHECKMONITORPOWERSTATE (d3dkmthk.h)
description: The D3DKMT_CHECKMONITORPOWERSTATE structure describes the connection to the monitor for which to check the power state.
old-location: display\d3dkmt_checkmonitorpowerstate.htm
ms.assetid: aa7cee9a-5051-4ebc-be7c-ac9ac91ba631
ms.date: 05/10/2018
keywords: ["D3DKMT_CHECKMONITORPOWERSTATE structure"]
ms.keywords: D3DKMT_CHECKMONITORPOWERSTATE, D3DKMT_CHECKMONITORPOWERSTATE structure [Display Devices], OpenGL_Structs_2c4ec2cb-c35a-4447-8e35-dc8e4964e8b2.xml, _D3DKMT_CHECKMONITORPOWERSTATE, d3dkmthk/D3DKMT_CHECKMONITORPOWERSTATE, display.d3dkmt_checkmonitorpowerstate
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
req.typenames: D3DKMT_CHECKMONITORPOWERSTATE
f1_keywords:
 - _D3DKMT_CHECKMONITORPOWERSTATE
 - d3dkmthk/_D3DKMT_CHECKMONITORPOWERSTATE
 - D3DKMT_CHECKMONITORPOWERSTATE
 - d3dkmthk/D3DKMT_CHECKMONITORPOWERSTATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMT_CHECKMONITORPOWERSTATE
---

# _D3DKMT_CHECKMONITORPOWERSTATE structure


## -description

The D3DKMT_CHECKMONITORPOWERSTATE structure describes the connection to the monitor for which to check the power state.

## -struct-fields

### -field hAdapter

[in] A handle to the graphics adapter.

### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the monitor is connected to.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcheckmonitorpowerstate">D3DKMTCheckMonitorPowerState</a>