---
UID: NS:d3dumddi._D3DDDICB_QUERYADAPTERINFO
title: _D3DDDICB_QUERYADAPTERINFO (d3dumddi.h)
description: The D3DDDICB_QUERYADAPTERINFO structure contains information that describes the graphics adapter.
old-location: display\d3dddicb_queryadapterinfo.htm
tech.root: display
ms.assetid: 484406a5-54be-49fa-839a-2e55747020f4
ms.date: 05/10/2018
ms.keywords: D3DDDICB_QUERYADAPTERINFO, D3DDDICB_QUERYADAPTERINFO structure [Display Devices], D3D_param_Structs_24ed4d09-d2ff-4b79-95fc-5a1c7d146faa.xml, _D3DDDICB_QUERYADAPTERINFO, d3dumddi/D3DDDICB_QUERYADAPTERINFO, display.d3dddicb_queryadapterinfo
ms.topic: struct
f1_keywords:
 - "d3dumddi/D3DDDICB_QUERYADAPTERINFO"
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
- D3DDDICB_QUERYADAPTERINFO
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_QUERYADAPTERINFO
---

# _D3DDDICB_QUERYADAPTERINFO structure


## -description


The D3DDDICB_QUERYADAPTERINFO structure contains information that describes the graphics adapter.


## -struct-fields




### -field pPrivateDriverData

[out] A pointer to a buffer that the display miniport driver can fill with information about the graphics adapter.


### -field PrivateDriverDataSize

[in/out] The size, in bytes, of the buffer that <b>pPrivateDriverData</b> points to.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryadapterinfocb">pfnQueryAdapterInfoCb</a>
 

 

