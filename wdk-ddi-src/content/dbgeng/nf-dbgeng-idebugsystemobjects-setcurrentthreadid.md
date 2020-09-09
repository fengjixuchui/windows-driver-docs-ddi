---
UID: NF:dbgeng.IDebugSystemObjects.SetCurrentThreadId
title: IDebugSystemObjects::SetCurrentThreadId (dbgeng.h)
description: The SetCurrentThreadId method makes the specified thread the current thread.
old-location: debugger\setcurrentthreadid.htm
tech.root: debugger
ms.assetid: 965c2fe0-5be5-4036-b649-a25fcc6e2dc2
ms.date: 05/03/2018
keywords: ["IDebugSystemObjects::SetCurrentThreadId"]
ms.keywords: IDebugSystemObjects interface [Windows Debugging],SetCurrentThreadId method, IDebugSystemObjects.SetCurrentThreadId, IDebugSystemObjects2 interface [Windows Debugging],SetCurrentThreadId method, IDebugSystemObjects2::SetCurrentThreadId, IDebugSystemObjects3 interface [Windows Debugging],SetCurrentThreadId method, IDebugSystemObjects3::SetCurrentThreadId, IDebugSystemObjects4 interface [Windows Debugging],SetCurrentThreadId method, IDebugSystemObjects4::SetCurrentThreadId, IDebugSystemObjects::SetCurrentThreadId, IDebugSystemObjects_61d7341c-41f8-4971-ad7e-b4fbd5b022b1.xml, SetCurrentThreadId, SetCurrentThreadId method [Windows Debugging], SetCurrentThreadId method [Windows Debugging],IDebugSystemObjects interface, SetCurrentThreadId method [Windows Debugging],IDebugSystemObjects2 interface, SetCurrentThreadId method [Windows Debugging],IDebugSystemObjects3 interface, SetCurrentThreadId method [Windows Debugging],IDebugSystemObjects4 interface, dbgeng/IDebugSystemObjects2::SetCurrentThreadId, dbgeng/IDebugSystemObjects3::SetCurrentThreadId, dbgeng/IDebugSystemObjects4::SetCurrentThreadId, dbgeng/IDebugSystemObjects::SetCurrentThreadId, debugger.setcurrentthreadid
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
 - IDebugSystemObjects::SetCurrentThreadId
 - dbgeng/IDebugSystemObjects::SetCurrentThreadId
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSystemObjects.SetCurrentThreadId
 - IDebugSystemObjects2.SetCurrentThreadId
 - IDebugSystemObjects3.SetCurrentThreadId
 - IDebugSystemObjects4.SetCurrentThreadId
---

# IDebugSystemObjects::SetCurrentThreadId


## -description

The <b>SetCurrentThreadId</b> method makes the specified thread the current thread.

## -parameters

### -param Id 

[in]
Specifies the engine thread ID of the thread that is to become the current thread.

## -returns

This method may also return other error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
No thread with the specified ID was found.

</td>
</tr>
</table>

## -remarks

This method may also change the current process, current target, and current computer.

If the thread is changed, the callback <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-changeenginestate">IDebugEventCallbacks::ChangeEngineState</a> will be called with the DEBUG_CES_CURRENT_THREAD bit set.

<div class="alert"><b>Note</b>    In kernel-mode debugging, the current thread is a virtual thread, it is not a system thread.  This method cannot be used to change between system threads in kernel-mode debugging.  However, the implicit thread may be changed by using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-setimplicitthreaddataoffset">SetImplicitThreadDataOffset</a>.</div>
<div> </div>
For more information about threads, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.  For details on monitoring events, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/monitoring-events">Monitoring Events</a>.

