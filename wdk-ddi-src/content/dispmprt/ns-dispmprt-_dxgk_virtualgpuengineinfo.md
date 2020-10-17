---
UID: NS:dispmprt._DXGK_VIRTUALGPUENGINEINFO
title: _DXGK_VIRTUALGPUENGINEINFO
description: The virtual GPU engine info.
tech.root: display
ms.assetid: aa646d1b-2a8c-4d5a-9cdd-2d7fc4ae68c8
ms.date: 04/04/2019
keywords: ["DXGK_VIRTUALGPUENGINEINFO structure"]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGK_VIRTUALGPUENGINEINFO, DXGK_VIRTUALGPUENGINEINFO, *PDXGK_VIRTUALGPUENGINEINFO,
req.header: dispmprt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGK_VIRTUALGPUENGINEINFO, *PDXGK_VIRTUALGPUENGINEINFO
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _DXGK_VIRTUALGPUENGINEINFO
 - dispmprt/_DXGK_VIRTUALGPUENGINEINFO
 - PDXGK_VIRTUALGPUENGINEINFO
 - dispmprt/PDXGK_VIRTUALGPUENGINEINFO
 - DXGK_VIRTUALGPUENGINEINFO
 - dispmprt/DXGK_VIRTUALGPUENGINEINFO
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_VIRTUALGPUENGINEINFO
product:
 - Windows
dev_langs:
 - c++
---

# _DXGK_VIRTUALGPUENGINEINFO structure


## -description

The virtual GPU engine info.

## -struct-fields

### -field MinPartitionUnits

Minimum engine partition units, which should be used with the engine.

### -field MaxPartitionUnits

Maximum engine partition units, which should be used with the engine.

### -field EngineId

 
An index to the engine array.

## -remarks

When a vGPU is created successfully, all resources must be allocated, but hardware register are not mapped yet. The vGPU will be switched to the running state when DxgkDdiSetVirtualFunctionPowerState is called with the D0 state.  This data structure is deprecated and should be zero if used.

## -see-also

