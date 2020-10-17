---
UID: NF:dbgeng.IDebugControl4.SetEventFilterCommandWide
title: IDebugControl4::SetEventFilterCommandWide (dbgeng.h)
description: The SetEventFilterCommandWide method sets a debugger command for the engine to execute when a specified event occurs.
old-location: debugger\seteventfiltercommandwide.htm
tech.root: debugger
ms.assetid: e0e14c8b-0b11-482f-93e2-31c522235110
ms.date: 05/03/2018
keywords: ["IDebugControl4::SetEventFilterCommandWide"]
ms.keywords: IDebugControl4 interface [Windows Debugging],SetEventFilterCommandWide method, IDebugControl4.SetEventFilterCommandWide, IDebugControl4::SetEventFilterCommandWide, SetEventFilterCommandWide, SetEventFilterCommandWide method [Windows Debugging], SetEventFilterCommandWide method [Windows Debugging],IDebugControl4 interface, dbgeng/IDebugControl4::SetEventFilterCommandWide, debugger.seteventfiltercommandwide
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugControl4::SetEventFilterCommandWide
 - dbgeng/IDebugControl4::SetEventFilterCommandWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl4.SetEventFilterCommandWide
---

# IDebugControl4::SetEventFilterCommandWide


## -description

The <b>SetEventFilterCommandWide</b>  method sets a debugger command for the engine to execute when a specified event occurs.

## -parameters

### -param Index 

[in]
Specifies the index of the event filter.  <i>Index</i> can take any value between zero and one less than the total number of event filters returned by <b>GetNumberEventFilters</b> (inclusive).  For more information about the index of the filters, see Index and Exception Code.

### -param Command 

[in]
Specifies the debugger command for the engine to execute when the event occurs.

## -returns

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

## -remarks

For more information about event filters, see <a href="/windows-hardware/drivers/debugger/event-filters">Event Filters</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-geteventfiltercommand">GetEventFilterCommand</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setexceptionfiltersecondcommand">SetExceptionFilterSecondCommand</a>



<a href="/windows-hardware/drivers/debugger/sx--sxd--sxe--sxi--sxn--sxr--sx---set-exceptions-">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>