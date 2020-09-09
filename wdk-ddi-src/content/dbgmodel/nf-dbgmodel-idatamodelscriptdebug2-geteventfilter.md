---
UID: NF:dbgmodel.IDataModelScriptDebug2.GetEventFilter
title: IDataModelScriptDebug2::GetEventFilter (dbgmodel.h)
description: The GetEventFilter method returns whether "break on event" is enabled for a particular event.
ms.assetid: 2b938d66-cd1f-4499-b190-a1481b50d19f
ms.date: 08/21/2018
keywords: ["IDataModelScriptDebug2::GetEventFilter"]
ms.keywords: IDataModelScriptDebug2::GetEventFilter, GetEventFilter, IDataModelScriptDebug2.GetEventFilter, IDataModelScriptDebug2::GetEventFilter, IDataModelScriptDebug2.GetEventFilter
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDataModelScriptDebug2::GetEventFilter
 - dbgmodel/IDataModelScriptDebug2::GetEventFilter
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelScriptDebug2.GetEventFilter
---

# IDataModelScriptDebug2::GetEventFilter


## -description

The GetEventFilter method returns whether "break on event" is enabled for a particular event. Events which can cause "break on event" are described by a member of the ScriptDebugEventFilter enumeration which is defined as follows: 

Enumerant |	Description
|---------|-------------|
ScriptDebugEventFilterEntry |	Indicates that a break on every entry into the script from the outside should break into the debugger. The moment the scripting engine makes any call into script code, an immediate break should occur.
ScriptDebugEventFilterException |	Indicates that the debugger should break whenever an exception occurs (what some debuggers might call a first chance exception). This break should occur before the event is handled in any way by script code.
ScriptDebugEventFilterUnhandledException |	Indicates that the debugger should break if an unhandled exception occurs.
ScriptDebugEventFilterAbort |	Indicates that the debugger should break if an abort occurs rather than simply aborting script execution.

If a particular event type is not supported by the script debugger, E_NOTIMPL may be returned. 

As long as the script debugger is enabled via a call to the StartDebugging method, it is legal to call this method.

## -parameters

### -param eventFilter

Indicates for which event the "break on event" behavior is being changed. The event is defined as a member of the ScriptDebugEventFilter enumeration.

### -param isBreakEnabled

If "break on event" is enabled for the event in question, true is returned; otherwise, false is returned.

## -returns

This method returns HRESULT that indicates success or failure.

## -see-also

[IDataModelScriptDebug2 interface](nn-dbgmodel-idatamodelscriptdebug2.md)

