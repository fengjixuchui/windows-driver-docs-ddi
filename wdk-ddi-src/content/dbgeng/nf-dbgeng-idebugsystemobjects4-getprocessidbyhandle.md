---
UID: NF:dbgeng.IDebugSystemObjects4.GetProcessIdByHandle
title: IDebugSystemObjects4::GetProcessIdByHandle (dbgeng.h)
description: The GetProcessIdByHandle method returns the engine process ID for the specified process. The process is specified by its system handle.
old-location: debugger\getprocessidbyhandle.htm
tech.root: debugger
ms.assetid: 6920cbd3-0a20-4d38-8538-85f46d0f0d5b
ms.date: 05/03/2018
keywords: ["IDebugSystemObjects4::GetProcessIdByHandle"]
ms.keywords: GetProcessIdByHandle, GetProcessIdByHandle method [Windows Debugging], GetProcessIdByHandle method [Windows Debugging],IDebugSystemObjects interface, GetProcessIdByHandle method [Windows Debugging],IDebugSystemObjects2 interface, GetProcessIdByHandle method [Windows Debugging],IDebugSystemObjects3 interface, GetProcessIdByHandle method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects interface [Windows Debugging],GetProcessIdByHandle method, IDebugSystemObjects2 interface [Windows Debugging],GetProcessIdByHandle method, IDebugSystemObjects2::GetProcessIdByHandle, IDebugSystemObjects3 interface [Windows Debugging],GetProcessIdByHandle method, IDebugSystemObjects3::GetProcessIdByHandle, IDebugSystemObjects4 interface [Windows Debugging],GetProcessIdByHandle method, IDebugSystemObjects4.GetProcessIdByHandle, IDebugSystemObjects4::GetProcessIdByHandle, IDebugSystemObjects::GetProcessIdByHandle, IDebugSystemObjects_92e69c0f-a50c-498b-8352-74f0c28ea0d8.xml, dbgeng/IDebugSystemObjects2::GetProcessIdByHandle, dbgeng/IDebugSystemObjects3::GetProcessIdByHandle, dbgeng/IDebugSystemObjects4::GetProcessIdByHandle, dbgeng/IDebugSystemObjects::GetProcessIdByHandle, debugger.getprocessidbyhandle
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
 - IDebugSystemObjects4::GetProcessIdByHandle
 - dbgeng/IDebugSystemObjects4::GetProcessIdByHandle
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSystemObjects.GetProcessIdByHandle
 - IDebugSystemObjects2.GetProcessIdByHandle
 - IDebugSystemObjects3.GetProcessIdByHandle
 - IDebugSystemObjects4.GetProcessIdByHandle
---

# IDebugSystemObjects4::GetProcessIdByHandle


## -description

The <b>GetProcessIdByHandle</b> method returns the engine process ID for the specified process.  The process is specified by its system handle.

## -parameters

### -param Handle 

[in]
Specifies the handle of the process whose process ID is requested.  This handle must be a process handle previously retrieved from the debugger engine.

### -param Id 

[out]
Receives the engine process ID.

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

For more information about processes, see <a href="/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.  For details on system handles, see <a href="/windows-hardware/drivers/">Handles</a>.