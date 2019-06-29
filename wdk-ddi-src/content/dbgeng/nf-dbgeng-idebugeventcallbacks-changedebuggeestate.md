---
UID: NF:dbgeng.IDebugEventCallbacks.ChangeDebuggeeState
title: IDebugEventCallbacks::ChangeDebuggeeState (dbgeng.h)
description: The ChangeDebuggeeState callback method is called by the engine when it makes or detects changes to the target.
old-location: debugger\idebugeventcallbacks_changedebuggeestate.htm
tech.root: debugger
ms.assetid: 157a420a-18ad-46cf-ae93-603e9226ee4f
ms.date: 05/03/2018
ms.keywords: ChangeDebuggeeState, ChangeDebuggeeState method [Windows Debugging], ChangeDebuggeeState method [Windows Debugging],IDebugEventCallbacks interface, ComCallbacks_a5743ecf-0b4c-41de-9384-ee0d8980a746.xml, IDebugEventCallbacks interface [Windows Debugging],ChangeDebuggeeState method, IDebugEventCallbacks.ChangeDebuggeeState, IDebugEventCallbacks::ChangeDebuggeeState, dbgeng/IDebugEventCallbacks::ChangeDebuggeeState, debugger.idebugeventcallbacks_changedebuggeestate
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
- IDebugEventCallbacks.ChangeDebuggeeState
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugEventCallbacks::ChangeDebuggeeState


## -description


The <b>ChangeDebuggeeState</b> callback method is called by the engine when it makes or detects changes to the target.


## -parameters




### -param Flags [in]

Specifies the type of changes made to the target.  <i>Flags</i> may take one of the following values:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_CDS_ALL

</td>
<td>
A general change in the target has occurred. For example, the target has been executing, or the engine has just attached to the target.

</td>
</tr>
<tr>
<td>
DEBUG_CDS_REGISTERS

</td>
<td>
The processor registers for the target have changed.

</td>
</tr>
<tr>
<td>
DEBUG_CDS_DATA

</td>
<td>
The target's data space has changed.

</td>
</tr>
<tr>
<td>
DEBUG_CDS_REFRESH

</td>
<td>
Inform the GUI clients to refresh debugger windows.

</td>
</tr>
</table>
 


### -param Argument [in]

Provides additional information about the change in the target. The interpretation of the value of <i>Argument</i> depends on the value of <i>Flags</i>:

<dl>
<dt><a id="DEBUG_CDS_ALL"></a><a id="debug_cds_all"></a>DEBUG_CDS_ALL</dt>
<dd>
The value of <i>Argument</i> is zero.

</dd>
<dt><a id="DEBUG_CDS_REGISTERS"></a><a id="debug_cds_registers"></a>DEBUG_CDS_REGISTERS</dt>
<dd>
If a single register has changed, the value of <i>Argument</i> is the index of that register.  Otherwise, the value of <i>Argument</i> is DEBUG_ANY_ID.

</dd>
<dt><a id="DEBUG_CDS_DATA"></a><a id="debug_cds_data"></a>DEBUG_CDS_DATA</dt>
<dd>
The value of <i>Argument</i> specifies which data space was changed.  The following table contains the possible values of <i>Argument</i>.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_DATA_SPACE_VIRTUAL

</td>
<td>
The target's virtual memory has changed.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_SPACE_PHYSICAL

</td>
<td>
The target's physical memory has changed.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_SPACE_CONTROL

</td>
<td>
The target's control memory has changed.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_SPACE_IO

</td>
<td>
The target's I/O ports have received input or output.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_SPACE_MSR

</td>
<td>
The target's Model-Specific Registers (MSRs) have changed.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_SPACE_BUS_DATA

</td>
<td>
The target's bus memory has changed.

</td>
</tr>
</table>
 

</dd>
<dt><a id="DEBUG_CDS_REFRESH"></a><a id="debug_cds_refresh"></a>DEBUG_CDS_REFRESH</dt>
<dd>
The following table contains the possible values of <i>Argument</i>.

<table>
<tr>
<th>Value</th>
</tr>
<tr>
<td>
DEBUG_CDS_REFRESH_EVALUATE

</td>
</tr>
<tr>
<td>
DEBUG_CDS_REFRESH_EXECUTE

</td>
</tr>
<tr>
<td>
DEBUG_CDS_REFRESH_EXECUTECOMMANDFILE

</td>
</tr>
<tr>
<td>
DEBUG_CDS_REFRESH_ADDBREAKPOINT 

</td>
</tr>
<tr>
<td>
DEBUG_CDS_REFRESH_REMOVEBREAKPOINT

</td>
</tr>
<tr>
<td>
DEBUG_CDS_REFRESH_WRITEVIRTUAL

</td>
</tr>
<tr>
<td>
DEBUG_CDS_REFRESH_WRITEVIRTUALUNCACHED

</td>
</tr>
<tr>
<td>
DEBUG_CDS_REFRESH_WRITEPHYSICAL

</td>
</tr>
<tr>
<td>
DEBUG_CDS_REFRESH_WRITEPHYSICAL2

</td>
</tr>
<tr>
<td>
DEBUG_CDS_REFRESH_SETVALUE

</td>
</tr>
<tr>
<td>
DEBUG_CDS_REFRESH_SETVALUE2

</td>
</tr>
<tr>
<td>
DEBUG_CDS_REFRESH_SETSCOPE

</td>
</tr>
<tr>
<td>
DEBUG_CDS_REFRESH_SETSCOPEFRAMEBYINDEX

</td>
</tr>
<tr>
<td>
DEBUG_CDS_REFRESH_SETSCOPEFROMJITDEBUGINFO

</td>
</tr>
<tr>
<td>
DEBUG_CDS_REFRESH_SETSCOPEFROMSTOREDEVENT

</td>
</tr>
<tr>
<td>
DEBUG_CDS_REFRESH_INLINESTEP

</td>
</tr>
<tr>
<td>
DEBUG_CDS_REFRESH_INLINESTEP_PSEUDO

</td>
</tr>
</table>
 

</dd>
</dl>



## -returns



The return value is ignored by the engine unless it indicates a remote procedure call error; in this case the client, with which this <b>IDebugEventCallbacks</b> object is registered, is disabled.




## -remarks



The engine calls <b>ChangeDebuggeeState</b> only if the DEBUG_EVENT_CHANGE_DEBUGGEE_STATE flag is set in the mask returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-getinterestmask">IDebugEventCallbacks::GetInterestMask</a>.

For more information about handling events, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/monitoring-events">Monitoring Events</a>.  For information about managing the target's memory, including registers and data spaces, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/memory-access">Memory Access</a>.  For information about the target's virtual and physical memory, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/virtual-and-physical-memory">Virtual and Physical Memory</a>.  For information about the target's control memory, I/O ports, MSR, and bus memory, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/other-data-spaces">Other Data Spaces</a>.



