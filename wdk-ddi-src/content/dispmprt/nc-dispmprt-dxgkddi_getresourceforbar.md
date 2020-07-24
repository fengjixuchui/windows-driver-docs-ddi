---
UID: NC:dispmprt.DXGKDDI_GETRESOURCEFORBAR
title: DXGKDDI_GETRESOURCEFORBAR
author: windows-driver-content
description: If the driver does not support the GUID_DXGKDDI_FLEXIOV_DEVICE_INTERFACE interface, this routine returns the host partition base address of a single Virtual Function base address register.
tech.root: display
ms.assetid: ebbcca1e-fa42-4441-b5a0-7450937391af
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["DXGKDDI_GETRESOURCEFORBAR callback function"]
f1_keywords:
 - "dispmprt/DXGKDDI_GETRESOURCEFORBAR"
 - "DXGKDDI_GETRESOURCEFORBAR"
req.header: dispmprt.h
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
topic_type: 
 - apiref
api_type: 
 - UserDefined
api_location: 
 - dispmprt.h
api_name: 
 - DXGKDDI_GETRESOURCEFORBAR
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# DXGKDDI_GETRESOURCEFORBAR callback function

## -description

If the driver does not support the GUID_DXGKDDI_FLEXIOV_DEVICE_INTERFACE interface, this routine returns the host partition base address of a single Virtual Function base address register. This host physical address should be the beginning of the MMIO (Memory management input output) space that the driver wants to be mapped as the GPU partition’s MMIO bar.

When the driver report that it does support the GUID_DXGKDDI_FLEXIOV_DEVICE_INTERFACE interface, this function will not be called.

## -prototype

```
//Declaration

DXGKDDI_GETRESOURCEFORBAR DxgkddiGetresourceforbar; 

// Definition

NTSTATUS DxgkddiGetresourceforbar 
(
	HANDLE Context
	DXGKARG_GETRESOURCEFORBAR * pArgs
)
{...}

```

## -parameters

### -param Context

[in] The miniport context that is returned by the driver in the [DXGKDDI_SRIOV_INTERFACE](ns-dispmprt-_dxgkddi_sriov_interface.md) structure.

### -param pArgs 

[in, out] A pointer to the DXGKARG_GETRESOURCEFORBAR that contains arguments for this function.

## -returns

If the VF has resources at this BarIndex and can return the information correct, the statement NT_SUCCESS(return value) will be true.

## -remarks

This routine can fail if the VF does not expose a BAR at BarIndex.  This is expected and will not cause an immediate failure.


## -see-also
