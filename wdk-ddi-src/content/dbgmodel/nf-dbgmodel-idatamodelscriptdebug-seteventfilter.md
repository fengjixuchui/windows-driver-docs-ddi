---
UID: NF:dbgmodel.IDataModelScriptDebug.SetEventFilter
title: IDataModelScriptDebug::SetEventFilter (dbgmodel.h)
description: The SetEventFilter method changes the "break on event" behavior for a particular event as defined by a member of the ScriptDebugEventFilter enumeration.
ms.assetid: f70bad43-2e27-413d-ae03-f97f26d49158
ms.date: 08/21/2018
ms.topic: method
f1_keywords:
 - "dbgmodel/IDataModelScriptDebug.SetEventFilter"
ms.keywords: IDataModelScriptDebug::SetEventFilter, SetEventFilter, IDataModelScriptDebug.SetEventFilter, IDataModelScriptDebug::SetEventFilter, IDataModelScriptDebug.SetEventFilter
req.header: dbgmodel.h
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
topic_type: 
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDataModelScriptDebug.SetEventFilter
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebug::SetEventFilter


## -description

The SetEventFilter method changes the "break on event" behavior for a particular event as defined by a member of the ScriptDebugEventFilter enumeration. A full list of available events (and a description of this enumeration) can be found in the documentation for the GetEventFilter method. 

If a particular event type is not supported by the script debugger, E_NOTIMPL may be returned. 

As long as the script debugger is enabled via a call to the StartDebugging method, it is legal to call this method. 


## -parameters

### -param eventFilter
Indicates for which event the "break on event" behavior is being changed. The event is defined as a member of the ScriptDebugEventFilter enumeration.


### -param isBreakEnabled
If true, indicates that the caller wants the debugger to break into the debugger when the given event occurs; if false, indicates that the caller does not want the debugger to break into the debugger when the given event occurs.


## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelScriptDebug interface](nn-dbgmodel-idatamodelscriptdebug.md)
