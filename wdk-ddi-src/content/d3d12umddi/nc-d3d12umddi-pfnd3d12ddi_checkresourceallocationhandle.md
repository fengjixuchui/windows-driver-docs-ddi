---
UID: NC:d3d12umddi.PFND3D12DDI_CHECKRESOURCEALLOCATIONHANDLE
title: PFND3D12DDI_CHECKRESOURCEALLOCATIONHANDLE (d3d12umddi.h)
description: Checks resource allocation handle.
ms.assetid: 627c14f1-f793-40a8-b52d-ba98f90d2d1b
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CHECKRESOURCEALLOCATIONHANDLE callback function"]
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CHECKRESOURCEALLOCATIONHANDLE"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CHECKRESOURCEALLOCATIONHANDLE
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CHECKRESOURCEALLOCATIONHANDLE callback function

## -description

Checks resource allocation handle.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

A resource handle.

## -returns

Returns D3DKMT_HANDLE.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CHECKRESOURCEALLOCATIONHANDLE Pfnd3d12ddiCheckresourceallocationhandle; 

// Definition

D3DKMT_HANDLE Pfnd3d12ddiCheckresourceallocationhandle 
(
	 D3D12DDI_HDEVICE
	 D3D10DDI_HRESOURCE
)
{...}

PFND3D12DDI_CHECKRESOURCEALLOCATIONHANDLE 


```

