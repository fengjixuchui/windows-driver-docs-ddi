---
UID: NC:d3d12umddi.PFND3D12DDI_CREATESCHEDULINGGROUPCONTEXTVIRTUAL_CB_0050
title: PFND3D12DDI_CREATESCHEDULINGGROUPCONTEXTVIRTUAL_CB_0050 (d3d12umddi.h)
description: Creates a virtual context associated with a scheduling group.
ms.assetid: 2f9548d8-0cde-42f4-9eee-ce1af049265b
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CREATESCHEDULINGGROUPCONTEXTVIRTUAL_CB_0050 callback function"]
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
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
 - "d3d12umddi/PFND3D12DDI_CREATESCHEDULINGGROUPCONTEXTVIRTUAL_CB_0050"
 - "PFND3D12DDI_CREATESCHEDULINGGROUPCONTEXTVIRTUAL_CB_0050"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATESCHEDULINGGROUPCONTEXTVIRTUAL_CB_0050
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CREATESCHEDULINGGROUPCONTEXTVIRTUAL_CB_0050 callback function

## -description

Creates a virtual context associated with a scheduling group.

## -parameters

### -param hRTSchedulingGroup

A D3D12DDI_HRTSCHEDULINGGROUP_0050 runtime handle type that represents the contexts associated with a hardware scheduling group.

### -param Arg2

A pointer to a [D3DDDICB_CREATECONTEXTVIRTUAL](../d3dumddi/ns-d3dumddi-_d3dddicb_createcontextvirtual.md) structure that describes the context to create.

## -returns

Returns HRESULT.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATESCHEDULINGGROUPCONTEXTVIRTUAL_CB_0050 Pfnd3d12ddiCreateschedulinggroupcontextvirtualCb0050; 

// Definition

HRESULT Pfnd3d12ddiCreateschedulinggroupcontextvirtualCb0050 
(
	D3D12DDI_HRTSCHEDULINGGROUP_0050 hRTSchedulingGroup
	D3DDDICB_CREATECONTEXTVIRTUAL *
)
{...}

```

## -remarks

This callback should be used with contexts that support virtual addressing.

## -see-also

