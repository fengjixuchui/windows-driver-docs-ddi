---
UID: NF:dbgeng.IDebugSystemObjects3.GetCurrentThreadSystemId
title: IDebugSystemObjects3::GetCurrentThreadSystemId (dbgeng.h)
description: The GetCurrentThreadSystemId method returns the system thread ID of the current thread.
old-location: debugger\getcurrentthreadsystemid.htm
tech.root: debugger
ms.assetid: b2e4d14c-a97f-4f57-b0ce-5a52a82c1690
ms.date: 05/03/2018
keywords: ["IDebugSystemObjects3::GetCurrentThreadSystemId"]
ms.keywords: GetCurrentThreadSystemId, GetCurrentThreadSystemId method [Windows Debugging], GetCurrentThreadSystemId method [Windows Debugging],IDebugSystemObjects interface, GetCurrentThreadSystemId method [Windows Debugging],IDebugSystemObjects2 interface, GetCurrentThreadSystemId method [Windows Debugging],IDebugSystemObjects3 interface, GetCurrentThreadSystemId method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects interface [Windows Debugging],GetCurrentThreadSystemId method, IDebugSystemObjects2 interface [Windows Debugging],GetCurrentThreadSystemId method, IDebugSystemObjects2::GetCurrentThreadSystemId, IDebugSystemObjects3 interface [Windows Debugging],GetCurrentThreadSystemId method, IDebugSystemObjects3.GetCurrentThreadSystemId, IDebugSystemObjects3::GetCurrentThreadSystemId, IDebugSystemObjects4 interface [Windows Debugging],GetCurrentThreadSystemId method, IDebugSystemObjects4::GetCurrentThreadSystemId, IDebugSystemObjects::GetCurrentThreadSystemId, IDebugSystemObjects_67dfdace-712e-4652-96bd-d4f073c2bf0f.xml, dbgeng/IDebugSystemObjects2::GetCurrentThreadSystemId, dbgeng/IDebugSystemObjects3::GetCurrentThreadSystemId, dbgeng/IDebugSystemObjects4::GetCurrentThreadSystemId, dbgeng/IDebugSystemObjects::GetCurrentThreadSystemId, debugger.getcurrentthreadsystemid
f1_keywords:
 - "dbgeng/IDebugSystemObjects.GetCurrentThreadSystemId"
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
- IDebugSystemObjects.GetCurrentThreadSystemId
- IDebugSystemObjects2.GetCurrentThreadSystemId
- IDebugSystemObjects3.GetCurrentThreadSystemId
- IDebugSystemObjects4.GetCurrentThreadSystemId
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSystemObjects3::GetCurrentThreadSystemId


## -description


The <b>GetCurrentThreadSystemId</b> method returns the system thread ID of the current thread.


## -parameters




### -param SysId [out]

Receives the system thread ID.


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

For more information about threads, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.



