---
UID: NC:d3dkmddi.DXGKDDI_SUBMITCOMMANDTOHWQUEUE
title: DXGKDDI_SUBMITCOMMANDTOHWQUEUE (d3dkmddi.h)
description: Invoked by the DirectX graphics kernel to append a DMA buffer to a GPU visible hardware queue.
ms.assetid: 4dec4717-b938-4960-8347-991e100537eb
ms.date: 10/19/2018
keywords: ["DXGKDDI_SUBMITCOMMANDTOHWQUEUE callback function"]
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL or DISPATCH_LEVEL
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
 - DXGKDDI_SUBMITCOMMANDTOHWQUEUE
 - d3dkmddi/DXGKDDI_SUBMITCOMMANDTOHWQUEUE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_SUBMITCOMMANDTOHWQUEUE
product:
 - Windows
dev_langs:
 - c++
---

# DXGKDDI_SUBMITCOMMANDTOHWQUEUE callback function


## -description

Invoked by the DirectX graphics kernel to append a DMA (direct memory access) buffer to a GPU visible hardware queue.

## -parameters

### -param hAdapter

A handle to the adapter.

### -param pSubmitCommandToHwQueue

Pointer to a [DXGKARG_SUBMITCOMMANDTOHWQUEUE](ns-d3dkmddi-_dxgkarg_submitcommandtohwqueue.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

DXGKDDI_SUBMITCOMMANDTOHWQUEUE DxgkddiSubmitcommandtohwqueue; 

// Definition

NTSTATUS DxgkddiSubmitcommandtohwqueue 
(
	IN_CONST_HANDLE hAdapter
	IN_CONST_PDXGKARG_SUBMITCOMMANDTOHWQUEUE pSubmitCommandToHwQueue
)
{...}

```

## -remarks

This call is the first part of a two step submission process.

WDDM synchronization class: [Zero Level](/windows-hardware/drivers/display/threading-and-synchronization-zero-level), no reentrancy within the same hardware queue

## -see-also