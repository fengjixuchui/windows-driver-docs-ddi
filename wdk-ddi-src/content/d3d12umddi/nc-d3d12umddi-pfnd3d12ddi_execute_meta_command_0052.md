---
UID: NC:d3d12umddi.PFND3D12DDI_EXECUTE_META_COMMAND_0052
title: PFND3D12DDI_EXECUTE_META_COMMAND_0052 (d3d12umddi.h)
description: Executes the meta-command.
ms.assetid: b86e2ba8-45be-4535-a3ac-00da77660f1d
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_EXECUTE_META_COMMAND_0052 callback function"]
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
 - PFND3D12DDI_EXECUTE_META_COMMAND_0052
 - d3d12umddi/PFND3D12DDI_EXECUTE_META_COMMAND_0052
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_EXECUTE_META_COMMAND_0052
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_EXECUTE_META_COMMAND_0052 callback function


## -description

Executes the meta-command.

## -parameters

### -param Arg1

A handle to the driver's data for the command list. The driver uses this region of memory to store internal data structures that are related to its command list.

### -param Arg2

A handle to the meta-command.

### -param Arg3

A pointer to void.

### -param Arg4

## -prototype

```cpp
//Declaration

PFND3D12DDI_EXECUTE_META_COMMAND_0052 Pfnd3d12ddiExecuteMetaCommand0052; 

// Definition

VOID Pfnd3d12ddiExecuteMetaCommand0052 
(
	D3D12DDI_HCOMMANDLIST Arg1
	D3D12DDI_HMETACOMMAND_0052 Arg2
	CONST void *
	SIZE_T Arg3
)
{...}

```

