---
UID: NC:d3dkmthk.PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT
title: PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT (d3dkmthk.h)
description: The PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT callback function checks the details of hardware support for multiplane overlays.
ms.assetid: d67108d9-c3fa-41dc-ac6f-79243c1f7b68
ms.date: 10/19/2018
keywords: ["PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT callback function"]
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
 - PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT
 - d3dkmthk/PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT
dev_langs:
 - c++
---

# PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT callback function

> [!NOTE] This function has been replaced by [PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3](nc-d3dkmthk-pfnd3dkmt_checkmultiplaneoverlaysupport3.md).


## -description

The PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT callback function checks the details of hardware support for multiplane overlays.

## -parameters

### -param Arg1

[in, out] Pointer to a [D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT](ns-d3dkmthk-_d3dkmt_checkmultiplaneoverlaysupport.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT Pfnd3dkmtCheckmultiplaneoverlaysupport; 

// Definition

NTSTATUS Pfnd3dkmtCheckmultiplaneoverlaysupport 
(
	D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT *
)
{...}

```

