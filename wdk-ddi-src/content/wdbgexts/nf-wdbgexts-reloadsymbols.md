---
UID: NF:wdbgexts.ReloadSymbols
title: ReloadSymbols function (wdbgexts.h)
description: The ReloadSymbols function deletes symbol information from the debugger so that it can be reloaded as needed. This function behaves the same way as the debugger command .reload.
old-location: debugger\reloadsymbols.htm
tech.root: debugger
ms.assetid: 5778f57c-52dd-43f4-b0f7-d07e0c40512b
ms.date: 05/03/2018
keywords: ["ReloadSymbols function"]
ms.keywords: ReloadSymbols, ReloadSymbols function [Windows Debugging], WdbgExts_Ref_c48c63b8-6c59-42f7-8a44-78462cbf653f.xml, debugger.reloadsymbols, wdbgexts/ReloadSymbols
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ReloadSymbols
 - wdbgexts/ReloadSymbols
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdbgexts.h
api_name:
 - ReloadSymbols
---

# ReloadSymbols function


## -description

The <b>ReloadSymbols</b> function deletes symbol information from the debugger so that it can be reloaded as needed.  This function behaves the same way as the debugger command <a href="/windows-hardware/drivers/debugger/-reload--reload-module-">.reload</a>.

## -parameters

### -param OPTIONAL

<p>Specifies the arguments for the debugger command <b>.reload</b>.  For example, setting <i>Arg</i> to <b>/u ntdll.dll</b> has the same effect as the command <b>.reload /u ntdll.dll</b>.</p>

## -see-also

<a href="/windows-hardware/drivers/debugger/-reload--reload-module-">.reload (Reload Module)</a>