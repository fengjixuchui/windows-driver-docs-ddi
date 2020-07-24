---
UID: NS:d3dumddi._DXVAHDDDI_STREAM_STATE_PRIVATE_DATA
title: _DXVAHDDDI_STREAM_STATE_PRIVATE_DATA (d3dumddi.h)
description: The DXVAHDDDI_STREAM_STATE_PRIVATE_DATA structure describes stream-state data that specifies a private stream state.
old-location: display\dxvahdddi_stream_state_private_data.htm
tech.root: display
ms.assetid: 1352392f-62d4-46aa-aa59-651309c36e6f
ms.date: 05/10/2018
keywords: ["_DXVAHDDDI_STREAM_STATE_PRIVATE_DATA structure"]
ms.keywords: DXVA2_Structs_4c06fc77-dcae-41fa-b831-c3918ddbf467.xml, DXVAHDDDI_STREAM_STATE_PRIVATE_DATA, DXVAHDDDI_STREAM_STATE_PRIVATE_DATA structure [Display Devices], _DXVAHDDDI_STREAM_STATE_PRIVATE_DATA, d3dumddi/DXVAHDDDI_STREAM_STATE_PRIVATE_DATA, display.dxvahdddi_stream_state_private_data
f1_keywords:
 - "d3dumddi/DXVAHDDDI_STREAM_STATE_PRIVATE_DATA"
 - "DXVAHDDDI_STREAM_STATE_PRIVATE_DATA"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_STREAM_STATE_PRIVATE_DATA is supported beginning with the Windows 7 operating system.
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
- d3dumddi.h
api_name:
- DXVAHDDDI_STREAM_STATE_PRIVATE_DATA
targetos: Windows
req.typenames: DXVAHDDDI_STREAM_STATE_PRIVATE_DATA
---

# _DXVAHDDDI_STREAM_STATE_PRIVATE_DATA structure


## -description


The DXVAHDDDI_STREAM_STATE_PRIVATE_DATA structure describes stream-state data that specifies a private stream state. 


## -struct-fields




### -field Guid

[in] A GUID that identifies the private stream state.  


### -field DataSize

[in] The size, in bytes, of the private stream-state data. 


### -field pData

[in/out] A pointer to the private stream-state data. The caller sets <b>pData</b> to <b>NULL</b> to retrieve the size of the private stream-state data. 


## -remarks



Unlike other stream states (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_dxvahdddi_stream_state">DXVAHDDDI_STREAM_STATE</a>), the Direct3D runtime does not maintain the private stream state. An application and the driver communicates the private stream state directly through a proprietary manner, which consists of setting and retrieving the private stream state. 

To set private stream state, the application causes the Direct3D runtime to specify the DXVAHDDDI_STREAM_STATE_PRIVATE state in the <b>State</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_dxvahd_setvideoprocessstreamstate">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a> structure in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessstreamstate">SetVideoProcessStreamState</a> function. To retrieve private stream state, the application causes the Direct3D runtime to call the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_getvideoprocessstreamstateprivate">GetVideoProcessStreamStatePrivate</a> function. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_dxvahd_setvideoprocessstreamstate">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_dxvahdddi_stream_state">DXVAHDDDI_STREAM_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_getvideoprocessstreamstateprivate">GetVideoProcessStreamStatePrivate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessstreamstate">SetVideoProcessStreamState</a>
 

 

