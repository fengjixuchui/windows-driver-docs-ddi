---
UID: NF:dbgeng.IDebugSymbols3.GetSourceEntryString
title: IDebugSymbols3::GetSourceEntryString (dbgeng.h)
description: Queries symbol information and returns locations in the target's memory.
old-location: debugger\idebugsymbols3_getsourceentrystring.htm
tech.root: debugger
ms.assetid: 4742F6DD-F7D6-4EF4-877B-C02630018C8E
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::GetSourceEntryString"]
ms.keywords: GetSourceEntryString, GetSourceEntryString method [Windows Debugging], GetSourceEntryString method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetSourceEntryString method, IDebugSymbols3.GetSourceEntryString, IDebugSymbols3::GetSourceEntryString, dbgeng/IDebugSymbols3::GetSourceEntryString, debugger.idebugsymbols3_getsourceentrystring
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
 - IDebugSymbols3::GetSourceEntryString
 - dbgeng/IDebugSymbols3::GetSourceEntryString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugSymbols3.GetSourceEntryString
---

# IDebugSymbols3::GetSourceEntryString


## -description

Queries symbol information and returns locations in the target's memory.

## -parameters

### -param Entry 

[in]
An entry as a <a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_symbol_source_entry">DEBUG_SYMBOL_SOURCE_ENTRY</a> structure.

### -param Which 

[in]
A value that determines which types to return.

### -param Buffer 

[out]
A pointer to a string buffer for the results.

### -param BufferSize 

[in]
The size of the buffer.

### -param StringSize 

[out, optional]
Pointer to the size of the string.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

This method can return multiple results for a source lookup. This allows for all possible results to be returned.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>