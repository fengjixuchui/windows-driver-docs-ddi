---
UID: NC:d3dkmddi.DXGKDDI_RESUMECONTEXT
title: DXGKDDI_RESUMECONTEXT (d3dkmddi.h)
description: Learn more about the DXGKDDI_RESUMECONTEXT callback function.
ms.date: 04/08/2024
keywords: ["DXGKDDI_RESUMECONTEXT callback function"]
req.header: d3dkmddi.h
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
tech.root: display
ms.custom: RS5
f1_keywords:
 - DXGKDDI_RESUMECONTEXT
 - d3dkmddi/DXGKDDI_RESUMECONTEXT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_RESUMECONTEXT
dev_langs:
 - c++
---

# DXGKDDI_RESUMECONTEXT callback function

## -description

**DxgkddiResumeContext** resumes a context. A context is created in a resumed state by default.

## -parameters

### -param hAdapter

[in] The hardware context to be resumed.

### -param pResumeContext

[in] Pointer a [**DXGKARG_RESUMECONTEXT**](ns-d3dkmddi-_dxgkarg_resumecontext.md) structure that contains information to resume the content.

## -returns

**DxgkddiResumeContext** returns STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS error code.

## -remarks

Register your implementation of this callback function by setting it in [**DRIVER_INITIALIZATION_DATA**](/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_driver_initialization_data).

## -see-also

[**DxgkddiSuspendContext**](nc-d3dkmddi-dxgkddi_suspendcontext.md)
