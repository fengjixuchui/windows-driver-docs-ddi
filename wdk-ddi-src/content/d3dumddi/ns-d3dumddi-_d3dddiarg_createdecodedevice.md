---
UID: NS:d3dumddi._D3DDDIARG_CREATEDECODEDEVICE
title: _D3DDDIARG_CREATEDECODEDEVICE (d3dumddi.h)
description: The D3DDDIARG_CREATEDECODEDEVICE structure describes a Microsoft DirectX Video Acceleration (DirectX VA) decode device to create.
old-location: display\d3dddiarg_createdecodedevice.htm
tech.root: display
ms.assetid: 15750301-da36-4341-8d5a-ab76a2edb970
ms.date: 05/10/2018
keywords: ["_D3DDDIARG_CREATEDECODEDEVICE structure"]
ms.keywords: D3DDDIARG_CREATEDECODEDEVICE, D3DDDIARG_CREATEDECODEDEVICE structure [Display Devices], UMDisplayDriver_param_Structs_eb54920e-5904-4a9d-bfac-fe71743b2726.xml, _D3DDDIARG_CREATEDECODEDEVICE, d3dumddi/D3DDDIARG_CREATEDECODEDEVICE, display.d3dddiarg_createdecodedevice
f1_keywords:
 - "d3dumddi/D3DDDIARG_CREATEDECODEDEVICE"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
- d3dumddi.h
api_name:
- D3DDDIARG_CREATEDECODEDEVICE
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_CREATEDECODEDEVICE
---

# _D3DDDIARG_CREATEDECODEDEVICE structure


## -description


The D3DDDIARG_CREATEDECODEDEVICE structure describes a Microsoft DirectX Video Acceleration (DirectX VA) decode device to create. 


## -struct-fields




### -field pGuid

[in] A pointer to the GUID that represents the DirectX VA decode type. The Microsoft Direct3D runtime calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a> function to query for the supported GUIDs.


### -field VideoDesc

[in] The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_videodesc">DXVADDI_VIDEODESC</a> structure for the video stream that the decode device should decode.


### -field pConfig

[in] A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_configpicturedecode">DXVADDI_CONFIGPICTUREDECODE</a> structure that contains the DirectX VA connection configuration data for compressed picture decoding that the decode device requires. The Direct3D runtime calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a> function to query for the supported configurations.


### -field hDecode

[in/out] A handle to the decode device. The user-mode display driver must set this handle to a value that the Direct3D runtime can use to identify the decode device in subsequent calls.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createdecodedevice">CreateDecodeDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_configpicturedecode">DXVADDI_CONFIGPICTUREDECODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_videodesc">DXVADDI_VIDEODESC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a>
 

 

