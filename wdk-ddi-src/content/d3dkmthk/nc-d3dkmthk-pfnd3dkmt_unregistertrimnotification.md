---
UID: NC:d3dkmthk.PFND3DKMT_UNREGISTERTRIMNOTIFICATION
title: PFND3DKMT_UNREGISTERTRIMNOTIFICATION (d3dkmthk.h)
description: PFND3DKMT_UNREGISTERTRIMNOTIFICATION callback function removes a callback registration for a kernel mode device receiving notifications from a graphics framework (such as OpenGL).
ms.assetid: 3e329473-b630-4e29-ace3-7ae0c2606198
ms.date: 10/19/2018
keywords: ["PFND3DKMT_UNREGISTERTRIMNOTIFICATION callback function"]
req.header: d3dkmthk.h
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
ms.custom: RS5
tech.root: display
f1_keywords:
 - PFND3DKMT_UNREGISTERTRIMNOTIFICATION
 - d3dkmthk/PFND3DKMT_UNREGISTERTRIMNOTIFICATION
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_UNREGISTERTRIMNOTIFICATION
dev_langs:
 - c++
---

# PFND3DKMT_UNREGISTERTRIMNOTIFICATION callback function


## -description

PFND3DKMT_UNREGISTERTRIMNOTIFICATION callback function removes a callback registration for a kernel mode device receiving notifications from a graphics framework (such as OpenGL).

## -parameters

### -param Arg1

Pointer to a [D3DKMT_UNREGISTERTRIMNOTIFICATION](ns-d3dkmthk-_d3dkmt_unregistertrimnotification.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_UNREGISTERTRIMNOTIFICATION Pfnd3dkmtUnregistertrimnotification; 

// Definition

NTSTATUS Pfnd3dkmtUnregistertrimnotification 
(
	D3DKMT_UNREGISTERTRIMNOTIFICATION *
)
{...}

```

## -remarks

## -see-also

