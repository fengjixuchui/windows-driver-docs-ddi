---
UID: NF:dbgeng.IDebugControl2.SetSystemErrorControl
title: IDebugControl2::SetSystemErrorControl (dbgeng.h)
description: The SetSystemErrorControl method sets the control values for handling system errors.
old-location: debugger\setsystemerrorcontrol.htm
tech.root: debugger
ms.assetid: 0ff15743-29df-44dc-a18b-ba8f7e49058e
ms.date: 05/03/2018
ms.keywords: IDebugControl interface [Windows Debugging],SetSystemErrorControl method, IDebugControl2 interface [Windows Debugging],SetSystemErrorControl method, IDebugControl2.SetSystemErrorControl, IDebugControl2::SetSystemErrorControl, IDebugControl3 interface [Windows Debugging],SetSystemErrorControl method, IDebugControl3::SetSystemErrorControl, IDebugControl::SetSystemErrorControl, IDebugControl_60e365d4-8645-469c-8973-9f2da168bba3.xml, SetSystemErrorControl, SetSystemErrorControl method [Windows Debugging], SetSystemErrorControl method [Windows Debugging],IDebugControl interface, SetSystemErrorControl method [Windows Debugging],IDebugControl2 interface, SetSystemErrorControl method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::SetSystemErrorControl, dbgeng/IDebugControl3::SetSystemErrorControl, dbgeng/IDebugControl::SetSystemErrorControl, debugger.setsystemerrorcontrol
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
- IDebugControl.SetSystemErrorControl
- IDebugControl2.SetSystemErrorControl
- IDebugControl3.SetSystemErrorControl
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl2::SetSystemErrorControl


## -description


The <b>SetSystemErrorControl</b> method sets the control values for handling system errors.


## -parameters




### -param OutputLevel [in]

Specifies the level at which system errors are printed to the engine's output.  If the level of the system error is less than or equal to <i>OutputLevel</i>, the error is printed to the debugger console.


### -param BreakLevel [in]

Specifies the level at which system errors break into the debugger.  If the level of the system error is less than or equal to <i>BreakLevel</i>, the error breaks into the debugger.


## -returns



This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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



The level of a system error can take one of the following three values, listed from lowest to highest: SLE_ERROR, SLE_MINORERROR, and SLE_WARNING.  These values are defined in Winuser.h.

When a system error occurs, the engine calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-systemerror">IDebugEventCallbacks::SystemError</a> method of the event callbacks.  If the level is less than or equal to the <i>BreakLevel</i> parameter, the error will break into the debugger.  If the level is greater than <i>BreakLevel</i>, the engine will proceed with execution in the target as indicated by the <b>IDebugEventCallbacks::SystemError</b> method calls.  For more information about how the engine proceeds after an event, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/monitoring-events">Monitoring Events</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getsystemerrorcontrol">GetSystemErrorControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-systemerror">IDebugEventCallbacks::SystemError</a>
 

 

