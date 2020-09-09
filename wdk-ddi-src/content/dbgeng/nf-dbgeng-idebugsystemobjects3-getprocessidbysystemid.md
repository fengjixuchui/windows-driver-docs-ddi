---
UID: NF:dbgeng.IDebugSystemObjects3.GetProcessIdBySystemId
title: IDebugSystemObjects3::GetProcessIdBySystemId (dbgeng.h)
description: The GetProcessIdBySystemId method returns the engine process ID for a process specified by its system process ID.
old-location: debugger\getprocessidbysystemid.htm
tech.root: debugger
ms.assetid: 7260f0ea-5e8b-4b08-8c8f-70216ffe54a9
ms.date: 05/03/2018
keywords: ["IDebugSystemObjects3::GetProcessIdBySystemId"]
ms.keywords: GetProcessIdBySystemId, GetProcessIdBySystemId method [Windows Debugging], GetProcessIdBySystemId method [Windows Debugging],IDebugSystemObjects interface, GetProcessIdBySystemId method [Windows Debugging],IDebugSystemObjects2 interface, GetProcessIdBySystemId method [Windows Debugging],IDebugSystemObjects3 interface, GetProcessIdBySystemId method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects interface [Windows Debugging],GetProcessIdBySystemId method, IDebugSystemObjects2 interface [Windows Debugging],GetProcessIdBySystemId method, IDebugSystemObjects2::GetProcessIdBySystemId, IDebugSystemObjects3 interface [Windows Debugging],GetProcessIdBySystemId method, IDebugSystemObjects3.GetProcessIdBySystemId, IDebugSystemObjects3::GetProcessIdBySystemId, IDebugSystemObjects4 interface [Windows Debugging],GetProcessIdBySystemId method, IDebugSystemObjects4::GetProcessIdBySystemId, IDebugSystemObjects::GetProcessIdBySystemId, IDebugSystemObjects_45c888bc-6771-4cd4-843e-aeafd8c6c6cb.xml, dbgeng/IDebugSystemObjects2::GetProcessIdBySystemId, dbgeng/IDebugSystemObjects3::GetProcessIdBySystemId, dbgeng/IDebugSystemObjects4::GetProcessIdBySystemId, dbgeng/IDebugSystemObjects::GetProcessIdBySystemId, debugger.getprocessidbysystemid
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
 - IDebugSystemObjects3::GetProcessIdBySystemId
 - dbgeng/IDebugSystemObjects3::GetProcessIdBySystemId
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSystemObjects.GetProcessIdBySystemId
 - IDebugSystemObjects2.GetProcessIdBySystemId
 - IDebugSystemObjects3.GetProcessIdBySystemId
 - IDebugSystemObjects4.GetProcessIdBySystemId
---

# IDebugSystemObjects3::GetProcessIdBySystemId


## -description

The <b>GetProcessIdBySystemId</b> method returns the engine process ID for a process specified by its system process ID.

## -parameters

### -param SysId 

[in]
Specifies the system process ID.

### -param Id 

[out]
Receives the engine process ID.

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
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The target is a kernel-mode target.

</td>
</tr>
</table>

## -remarks

This method is only available in user-mode debugging.

For more information about processes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.

