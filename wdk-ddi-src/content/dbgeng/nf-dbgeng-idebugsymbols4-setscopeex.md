---
UID: NF:dbgeng.IDebugSymbols4.SetScopeEx
title: IDebugSymbols4::SetScopeEx (dbgeng.h)
description: Sets the scope as an extended frame structure.
old-location: debugger\idebugsymbols4_setscopeex.htm
tech.root: debugger
ms.assetid: 22844EBB-9BE7-47C0-BE1F-075473430F11
ms.date: 05/03/2018
keywords: ["IDebugSymbols4::SetScopeEx"]
ms.keywords: IDebugSymbols4 interface [Windows Debugging],SetScopeEx method, IDebugSymbols4.SetScopeEx, IDebugSymbols4::SetScopeEx, SetScopeEx, SetScopeEx method [Windows Debugging], SetScopeEx method [Windows Debugging],IDebugSymbols4 interface, dbgeng/IDebugSymbols4::SetScopeEx, debugger.idebugsymbols4_setscopeex
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugSymbols4::SetScopeEx
 - dbgeng/IDebugSymbols4::SetScopeEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugSymbols4.SetScopeEx
---

# IDebugSymbols4::SetScopeEx


## -description

Sets the scope as an extended frame structure.

## -parameters

### -param InstructionOffset 

[in]
The offset of the instruction for the scope.

### -param ScopeFrame 

[in, optional]
The scope frame to set as a <a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_stack_frame_ex">DEBUG_STACK_FRAME_EX</a> structure.

### -param ScopeContext 

[in]
A pointer to a scope context.

### -param ScopeContextSize 

[in]
The size of the scope context.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_stack_frame_ex">DEBUG_STACK_FRAME_EX</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols4">IDebugSymbols4</a>