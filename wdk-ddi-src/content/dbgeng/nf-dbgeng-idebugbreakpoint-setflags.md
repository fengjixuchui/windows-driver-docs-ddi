---
UID: NF:dbgeng.IDebugBreakpoint.SetFlags
title: IDebugBreakpoint::SetFlags (dbgeng.h)
description: The SetFlags method sets the flags for a breakpoint.
old-location: debugger\setflags.htm
tech.root: debugger
ms.assetid: 126741ba-b373-466e-986d-44e33c841eee
ms.date: 05/03/2018
ms.keywords: ComOther_0fb1a5d9-2c1f-4966-9838-e7d0ae17a43f.xml, IDebugBreakpoint interface [Windows Debugging],SetFlags method, IDebugBreakpoint.SetFlags, IDebugBreakpoint2 interface [Windows Debugging],SetFlags method, IDebugBreakpoint2::SetFlags, IDebugBreakpoint::SetFlags, SetFlags, SetFlags method [Windows Debugging], SetFlags method [Windows Debugging],IDebugBreakpoint interface, SetFlags method [Windows Debugging],IDebugBreakpoint2 interface, dbgeng/IDebugBreakpoint2::SetFlags, dbgeng/IDebugBreakpoint::SetFlags, debugger.setflags
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
- COM
api_location:
- dbgeng.h
api_name:
- IDebugBreakpoint.SetFlags
- IDebugBreakpoint2.SetFlags
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugBreakpoint::SetFlags


## -description


The <b>SetFlags</b> method sets the flags for a breakpoint.


## -parameters




### -param Flags [in]

The new flags for the breakpoint.  <i>Flags</i> is a bit field. It replaces the existing flag bits.  For more information about the flag bit field and an explanation of each flag, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/controlling-breakpoint-flags-and-parameters">Controlling Breakpoint Flags and Parameters</a>.  You cannot change the DEBUG_BREAKPOINT_DEFERRED flag in the engine. This bit in <i>Flags</i> must always be zero.


## -returns



<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>
 

This method can also return error values.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.




## -remarks



For more information about breakpoint properties, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/controlling-breakpoint-flags-and-parameters">Controlling Breakpoint Flags and Parameters</a>.



