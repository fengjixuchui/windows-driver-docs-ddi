---
UID: NC:iddcx.PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE
title: PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE
<<<<<<< HEAD
author: windows-driver-content
description: PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE is a pointer to a system-implemented function that updates the display configuration for the remote session.
tech.root: display
ms.assetid: 8c2076ea-c798-4d19-8e1f-ffc8fea44237
ms.author: windowsdriverdev
ms.date: 09/24/2020
keywords: ["PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE callback pointer"]
=======
description: Pointer to the indirect display function IddCxAdapterDisplayConfigUpdate.
tech.root: display
ms.assetid: 8c2076ea-c798-4d19-8e1f-ffc8fea44237
ms.date: 04/04/2019
keywords: ["PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE callback function"]
>>>>>>> master
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: iddcx.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
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
ms.custom: 19H1
f1_keywords:
 - PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE
 - iddcx/PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - iddcx.h
api_name:
 - PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE
product:
 - Windows
dev_langs:
 - c++
---

# PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE callback function

## -description

**PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE** is a pointer to a system-implemented function that updates the display configuration for the remote session.

## -parameters

### -param DriverGlobals

[in] Pointer to an [**IDD_DRIVER_GLOBALS**](/windows-hardware/drivers/ddi/iddcx/ns-iddcx-idd_driver_globals) structure containing system-defined per-driver data.

### -param AdapterObject

[in] The adapter object of the remote adapter that the display configuration is specified for.

### -param pInArgs

[in] Input arguments.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate NTSTATUS Values error code.

## -prototype

```cpp
//Declaration

*PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE *PfnIddcxadapterdisplayconfigupdate;

// Definition

NTSTATUS *PfnIddcxadapterdisplayconfigupdate
(
    PIDD_DRIVER_GLOBALS DriverGlobals
    IDDCX_ADAPTER AdapterObject
    const IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE *pInArgs
)
{...}

```

## -remarks

An indirect display driver (IDD) should call [**IddCxAdapterDisplayConfigUpdate**](nf-iddcx-iddcxadapterdisplayconfigupdate.md) to update the display configuration. IDDs should not directly call the function that **PFN_IDDCXADAPTERDISPLAYCONFIGUPDATE** points to.

## -see-also

[**IddCxAdapterDisplayConfigUpdate**](nf-iddcx-iddcxadapterdisplayconfigupdate.md)
