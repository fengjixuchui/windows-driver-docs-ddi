---
UID: NF:dbgeng.IDebugSymbols5.SetScopeFrameByIndexEx
title: IDebugSymbols5::SetScopeFrameByIndexEx (dbgeng.h)
description: Sets the current frame by using an index.
old-location: debugger\idebugsymbols5_setscopeframebyindexex.htm
tech.root: debugger
ms.assetid: E0638C55-4160-48A5-9378-6AA9AAC8DC36
ms.date: 05/03/2018
keywords: ["IDebugSymbols5::SetScopeFrameByIndexEx"]
ms.keywords: IDebugSymbols5 interface [Windows Debugging],SetScopeFrameByIndexEx method, IDebugSymbols5.SetScopeFrameByIndexEx, IDebugSymbols5::SetScopeFrameByIndexEx, SetScopeFrameByIndexEx, SetScopeFrameByIndexEx method [Windows Debugging], SetScopeFrameByIndexEx method [Windows Debugging],IDebugSymbols5 interface, dbgeng/IDebugSymbols5::SetScopeFrameByIndexEx, debugger.idebugsymbols5_setscopeframebyindexex
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
 - IDebugSymbols5::SetScopeFrameByIndexEx
 - dbgeng/IDebugSymbols5::SetScopeFrameByIndexEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugSymbols5.SetScopeFrameByIndexEx
---

# IDebugSymbols5::SetScopeFrameByIndexEx


## -description

Sets the current frame by using an index.

## -parameters

### -param Flags 

[in]
A bit-set that contains options that affect the behavior of this method.

### -param Index 

[in]
An index by which to set the frame.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols5">IDebugSymbols5</a>