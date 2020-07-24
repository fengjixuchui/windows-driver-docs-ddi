---
UID: NC:d3dkmddi.DXGKDDI_RESTOREMEMORYFORHOTUPDATE
title: DXGKDDI_RESTOREMEMORYFORHOTUPDATE
author: windows-driver-content
description: Restores memory for driver hot update.
tech.root: display
ms.assetid: de5d59c6-2ce9-442c-866d-a64b3fa58952
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["DXGKDDI_RESTOREMEMORYFORHOTUPDATE callback function"]
f1_keywords:
 - "d3dkmddi/DXGKDDI_RESTOREMEMORYFORHOTUPDATE"
 - "DXGKDDI_RESTOREMEMORYFORHOTUPDATE"
req.header: d3dkmddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: <= APC_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
 - apiref
api_type: 
 - UserDefined
api_location: 
 - d3dkmddi.h
api_name: 
 - DXGKDDI_RESTOREMEMORYFORHOTUPDATE
targetos: Windows
dev_langs:
 - c++
ms.custom: DXGKDDI_INTERFACE_VERSION_WDDM2_6, 19H1
---

# DXGKDDI_RESTOREMEMORYFORHOTUPDATE callback function

## -description

Restores memory for driver hot update. This callback function does not initialize virtual functions. The driver needs to reserve resources, which are used to restore virtual GPUs.

## -prototype

```
//Declaration

DXGKDDI_RESTOREMEMORYFORHOTUPDATE DxgkddiRestorememoryforhotupdate; 

// Definition

NTSTATUS DxgkddiRestorememoryforhotupdate 
(
	IN_CONST_HANDLE hContext
	IN_CONST_PDXGKARG_RESTOREMEMORYFORHOTUPDATE pArgs
)
{...}

```

## -parameters

### -param hContext

[in] A handle to the driver miniport context.

### -param pArgs

[in] A pointer to the [DXGKARG_RESTOREMEMORYFORHOTUPDATE](ns-d3dkmddi-dxgkarg_restorememoryforhotupdate.md) structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds.

## -remarks

Before calling DxgkDdiStartDevice, Dxgkrnl calls **DxgkDdiRestoreMemoryForHotUpdate** once for each memory block, which was saved by [DxgkCbSaveMemoryForHotUpdate](nc-d3dkmddi-dxgkcb_savememoryforhotupdate.md).

## -see-also
