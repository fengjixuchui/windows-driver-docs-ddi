---
UID: NS:d3dkmthk._D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY
title: _D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY (d3dkmthk.h)
description: Describes information that is required for an in-process (in-proc) Microsoft Direct3D composition device to retrieve the scheduling priority for a device context that is in the same process as other device contexts.
old-location: display\d3dkmt_getcontextinprocessschedulingpriority.htm
ms.assetid: a72dd755-efd9-4950-8400-179eb1d63e9a
ms.date: 05/10/2018
keywords: ["_D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY structure"]
ms.keywords: D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY, D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY structure [Display Devices], _D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY, d3dkmthk/D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY, display.d3dkmt_getcontextinprocessschedulingpriority
f1_keywords:
 - "d3dkmthk/D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3dkmthk.h
api_name:
- D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY
---

# _D3DKMT_GETCONTEXTINPROCESSSCHEDULINGPRIORITY structure


## -description


Describes information that is required for an in-process (in-proc) Microsoft Direct3D composition device to retrieve the scheduling priority for a device context that is in the same process as other device contexts.


## -struct-fields




### -field hContext

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle to the device context to retrieve scheduling priority for.


### -field Priority

[out] The priority level that is retrieved for the device context relative to other device contexts within the same process.

A value of zero indicates that the context is scheduled with the same priority as other contexts within the same process.

A value of 1 indicates that the context is scheduled ahead of other contexts within the same process.

