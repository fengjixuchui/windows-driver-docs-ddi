---
UID: NS:d3dkmddi._DXGKARG_SWITCHTOHWCONTEXTLIST
title: _DXGKARG_SWITCHTOHWCONTEXTLIST (d3dkmddi.h)
description: Arguments used in the DXGKDDI_SWITCHTOHWCONTEXTLIST callback function.
ms.assetid: e856b8d8-c00e-4823-a9d2-647856bb10c0
ms.date: 10/19/2018
keywords: ["_DXGKARG_SWITCHTOHWCONTEXTLIST structure"]
f1_keywords:
 - "d3dkmddi/_DXGKARG_SWITCHTOHWCONTEXTLIST"
 - "_DXGKARG_SWITCHTOHWCONTEXTLIST"
ms.keywords: _DXGKARG_SWITCHTOHWCONTEXTLIST, DXGKARG_SWITCHTOHWCONTEXTLIST, 
req.header: d3dkmddi.h
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
req.typenames: DXGKARG_SWITCHTOHWCONTEXTLIST
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dkmddi.h
api_name: 
- _DXGKARG_SWITCHTOHWCONTEXTLIST
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# _DXGKARG_SWITCHTOHWCONTEXTLIST structure

## -description

Arguments used in the [DXGKDDI_SWITCHTOHWCONTEXTLIST](nc-d3dkmddi-dxgkddi_switchtohwcontextlist.md) callback function.

## -struct-fields

### -field hHwContextFirst

Hardware context that should be executed by the GPU first. If the GPU is currently not executing this context, it needs to preempt the current work and switch to *hHwContextFirst*. May be NULL if the GPU is instructed to become idle.

### -field hHwContextSecond

Hardware context that should be executed by the GPU once all queues in *hHwContextFirst* are idle or blocked on waits. May be NULL.

### -field NodeOrdinal

Node ordinal of engine that is instructed to switch to the new context(s).

### -field EngineOrdinal
 
Engine ordinal of engine that is instructed to switch to the new context(s).

## -remarks

## -see-also
