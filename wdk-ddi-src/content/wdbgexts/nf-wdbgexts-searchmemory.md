---
UID: NF:wdbgexts.SearchMemory
title: SearchMemory function (wdbgexts.h)
description: The SearchMemory function searches the target's virtual memory for a specified pattern of bytes.
old-location: debugger\searchmemory.htm
tech.root: debugger
ms.assetid: 7e07c47e-803b-44fa-9d0f-aa86475246d2
ms.date: 05/03/2018
ms.keywords: SearchMemory, SearchMemory function [Windows Debugging], WdbgExts_Ref_4eb909e5-edfd-487c-851c-812b15274c66.xml, debugger.searchmemory, wdbgexts/SearchMemory
ms.topic: function
f1_keywords:
 - "wdbgexts/SearchMemory"
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdbgexts.h
api_name:
- SearchMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# SearchMemory function


## -description


The <b>SearchMemory</b> function searches the target's virtual memory for a specified pattern of bytes.


## -parameters




### -param SearchAddress

Specifies the address in the target's virtual memory from which to start the search.


### -param SearchLength

Specifies the size, in bytes, of the memory to search.  For a successful match, the pattern must be found before <i>SearchLength</i> bytes have been examined.


### -param PatternLength

Specifies the size, in bytes, of the pattern to search for.


### -param Pattern

Specifies the pattern to search for.


### -param FoundAddress

Receives the location of the pattern, found in the target's virtual memory.  If the pattern was not found, the value in <i>FoundAddress</i> is unchanged by this function.


## -returns



None



