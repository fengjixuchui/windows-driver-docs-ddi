---
UID: NC:d3dkmthk.PFND3DKMT_OUTPUTDUPLGETMETADATA
title: PFND3DKMT_OUTPUTDUPLGETMETADATA (d3dkmthk.h)
description: The PFND3DKMT_OUTPUTDUPLGETMETADATA callback function gets output duplicate metadata.
ms.assetid: 1fcf334f-ebad-4a39-8357-ecc76ffec8e2
ms.date: 10/19/2018
keywords: ["PFND3DKMT_OUTPUTDUPLGETMETADATA callback function"]
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
 - PFND3DKMT_OUTPUTDUPLGETMETADATA
 - d3dkmthk/PFND3DKMT_OUTPUTDUPLGETMETADATA
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_OUTPUTDUPLGETMETADATA
dev_langs:
 - c++
---

# PFND3DKMT_OUTPUTDUPLGETMETADATA callback function


## -description

The PFND3DKMT_OUTPUTDUPLGETMETADATA callback function gets output duplicate metadata.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_OUTPUTDUPL_METADATA](ns-d3dkmthk-_d3dkmt_outputdupl_metadata.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_OUTPUTDUPLGETMETADATA Pfnd3dkmtOutputduplgetmetadata; 

// Definition

NTSTATUS Pfnd3dkmtOutputduplgetmetadata 
(
	D3DKMT_OUTPUTDUPL_METADATA *
)
{...}

```

## -remarks

## -see-also

