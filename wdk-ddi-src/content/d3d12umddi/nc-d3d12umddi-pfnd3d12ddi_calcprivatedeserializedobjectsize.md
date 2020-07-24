---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEDESERIALIZEDOBJECTSIZE
title: PFND3D12DDI_CALCPRIVATEDESERIALIZEDOBJECTSIZE (d3d12umddi.h)
description: CalcPrivateDeserializedObjectSize is called to get the size of the private driver data that the runtime should allocate for the driver to instantiate an object from serialized form.
tech.root: display
ms.assetid: a51ef44d-3323-4458-b03f-c5babe4ecc40
ms.date: 11/28/2018
keywords: ["PFND3D12DDI_CALCPRIVATEDESERIALIZEDOBJECTSIZE callback function"]
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10
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
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CALCPRIVATEDESERIALIZEDOBJECTSIZE"
 - "PFND3D12DDI_CALCPRIVATEDESERIALIZEDOBJECTSIZE"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALCPRIVATEDESERIALIZEDOBJECTSIZE
product:
 - Windows
---

# PFND3D12DDI_CALCPRIVATEDESERIALIZEDOBJECTSIZE callback function

## -description

CalcPrivateDeserializedObjectSize is called to get the size of the private driver data that the runtime should allocate for the driver to instantiate an object from serialized form.

## -parameters

### -param HDEVICE

Device handle.

### -param HandleType

Type of object being loaded.

### -param BlobSize

Size of serialized blob.

### -param pBlob

Serialized blob.

## -returns

Returns SIZE_T.

## -prototype

```
//Declaration

PFND3D12DDI_CALCPRIVATEDESERIALIZEDOBJECTSIZE Pfnd3d12ddiCalcprivatedeserializedobjectsize; 

// Definition

SIZE_T Pfnd3d12ddiCalcprivatedeserializedobjectsize 
(
	D3D12DDI_HDEVICE HDEVICE
	D3D12DDI_HANDLETYPE HandleType
	SIZE_T BlobSize
	 const UINT *pBlob
)
{...}

```

## -remarks

## -see-also

