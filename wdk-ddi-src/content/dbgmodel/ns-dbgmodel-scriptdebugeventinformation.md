---
UID: NS:dbgmodel.ScriptDebugEventInformation
title: ScriptDebugEventInformation (dbgmodel.h)
description: A struct containing information about a particular debug event.
ms.assetid: 33b3830f-8257-4dde-970f-2e21d7b7a831
ms.date: 07/16/2018
keywords: ["ScriptDebugEventInformation structure"]
ms.keywords: ScriptDebugEventInformation, ,
req.header: dbgmodel.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: 
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - ScriptDebugEventInformation
 - dbgmodel/ScriptDebugEventInformation
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dbgmodel.h
api_name:
 - ScriptDebugEventInformation
---

# ScriptDebugEventInformation structure


## -description

A struct containing information about a particular debug event.

## -struct-fields

### -field DebugEvent

### -field EventPosition

The line/column of script at which the debug event occurred (0 values : cannot determine)

### -field EventSpanEnd

The ending line/column of script at which the debug event occurred (0 values : cannot determine)

### -field u

### -field u.ExceptionInformation

### -field u.ExceptionInformation.IsUncaught

### -field u.BreakpointInformation

### -field u.BreakpointInformation.BreakpointId

## -remarks

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)

