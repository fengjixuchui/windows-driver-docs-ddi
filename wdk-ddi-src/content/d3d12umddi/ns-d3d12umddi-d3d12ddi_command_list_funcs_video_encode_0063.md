---
UID: NS:d3d12umddi.D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_ENCODE_0063
title: D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_ENCODE_0063
author: windows-driver-content
description: Command list functions for video encode, version D3D12DDI_FEATURE_VERSION_VIDEO_0063.
tech.root: display
ms.assetid: 8541d0db-814e-4a11-8577-f575d4ddb060
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: struct
ms.keywords: D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_ENCODE_0063, D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_ENCODE_0063,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_ENCODE_0063
targetos: Windows
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0043, 19H1
f1_keywords:
 - "d3d12umddi/D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_ENCODE_0063"
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_ENCODE_0063
product:
 - Windows
dev_langs:
 - c++
---

# D3D12DDI_COMMAND_LIST_FUNCS_VIDEO_ENCODE_0063 structure

## -description

Command list functions for video encode, version D3D12DDI_FEATURE_VERSION_VIDEO_0063.

## -struct-fields

### -field pfnCloseCommandList

Close command list.

### -field pfnResetCommandList

Reset command list.

### -field pfnDiscardResource

Discard resource.

### -field pfnSetMarker

Set marker.

### -field pfnSetPredication

Set predication.

### -field pfnBeginQuery

Begin query.

### -field pfnEndQuery

End query.

### -field pfnResolveQueryData

Resolve query data.

### -field pfnResourceBarrier

Resource barrier.

### -field pfnEstimateMotion

Decode frame.

### -field pfnSetProtectedResourceSession

Set protected resource session.

### -field pfnWriteBufferImmediate

Write buffer immediate.

### -field pfnResolveVideoMotionVectorHeap

 
Resolve video motion vector heap.

### -field pfnInitializeVideoExtensionCommand

Records a command to initialize or re-initialize a Video Extension Command into a command list.

### -field pfnExecuteVideoExtensionCommand

 
Records a command to execute a video extension command into a command list.

## -remarks

## -see-also

