---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_STATE_OBJECT_0054
title: PFND3D12DDI_CREATE_STATE_OBJECT_0054 (d3d12umddi.h)
description: Learn more about the PFND3D12DDI_CREATE_STATE_OBJECT_0054 callback function.
ms.date: 05/03/2024
keywords: ["PFND3D12DDI_CREATE_STATE_OBJECT_0054 callback function"]
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
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
 - PFND3D12DDI_CREATE_STATE_OBJECT_0054
 - d3d12umddi/PFND3D12DDI_CREATE_STATE_OBJECT_0054
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATE_STATE_OBJECT_0054
dev_langs:
 - c++
---

# PFND3D12DDI_CREATE_STATE_OBJECT_0054 callback function

## -description

UMD's **PFND3D12DDI_CREATE_STATE_OBJECT_0054** function creates a state object.

## -parameters

### -param unnamedParam1

[in] Handle to the device on which the state object is being created. It represents the GPU device on which all Direct3D 12 operations are performed.

### -param unnamedParam2

[in] Pointer to a [**D3D12DDIARG_CREATE_STATE_OBJECT_0054**](ns-d3d12umddi-d3d12ddiarg_create_state_object_0054.md) structure that describes the state object to create.

### -param unnamedParam3

[out] A **D3D12DDI_HSTATEOBJECT_0054** handle to the newly created state object returned by the function. This handle is used by the driver to reference the state object in subsequent operations.

### -param unnamedParam4

[in] Handle to a runtime (RT) state object. The runtime uses this handle to reference the state object in its own operations.

## -returns

**PFND3D12DDI_CREATE_STATE_OBJECT_0054** returns S_OK for success; otherwise it returns an appropriate error code.

## -remarks

A state object represents a variable amount of configuration state, including shaders, that an application manages as a single unit and which is given to a driver atomically to process (for example, to compile and optimize) however it sees fit. State objects are built out of subobjects. A [subobject](ns-d3d12umddi-d3d12ddi_state_subobject_0054.md) has a type and corresponding data.

## -see-also

[**D3D12DDIARG_CREATE_STATE_OBJECT_0054**](ns-d3d12umddi-d3d12ddiarg_create_state_object_0054.md)
