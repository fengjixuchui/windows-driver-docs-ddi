---
UID: NF:d3dkmthk.D3DKMTGetContextInProcessSchedulingPriority
title: D3DKMTGetContextInProcessSchedulingPriority function (d3dkmthk.h)
description: Called by an in-process (in-proc) Microsoft Direct3D composition device to retrieve the scheduling priority for a device context that is in the same process as other device contexts.
old-location: display\d3dkmtgetcontextinprocessschedulingpriority.htm
ms.assetid: e2a662b6-6a16-4e63-b5a8-5701a7180f60
ms.date: 05/10/2018
keywords: ["D3DKMTGetContextInProcessSchedulingPriority function"]
ms.keywords: D3DKMTGetContextInProcessSchedulingPriority, D3DKMTGetContextInProcessSchedulingPriority function [Display Devices], d3dkmthk/D3DKMTGetContextInProcessSchedulingPriority, display.d3dkmtgetcontextinprocessschedulingpriority
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTGetContextInProcessSchedulingPriority
 - d3dkmthk/D3DKMTGetContextInProcessSchedulingPriority
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
api_name:
 - D3DKMTGetContextInProcessSchedulingPriority
---

# D3DKMTGetContextInProcessSchedulingPriority function


## -description

Called by an in-process (in-proc) Microsoft Direct3D composition device to retrieve the scheduling priority for a device context that is in the same process as other device contexts.

## -parameters

### -param Arg1

*pContextPriority* [in, out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_getcontextinprocessschedulingpriority">D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY</a> structure that describes information that is required to retrieve the scheduling priority for a device context.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The scheduling priority was successfully retrieved.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other NTSTATUS values.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsetcontextinprocessschedulingpriority">D3DKMTSetContextInProcessSchedulingPriority</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_getcontextinprocessschedulingpriority">D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY</a>