---
UID: NF:dbgeng.IDebugClient2.GetOutputCallbacks
title: IDebugClient2::GetOutputCallbacks (dbgeng.h)
description: The GetOutputCallbacks method returns the output callbacks object registered with the client.
old-location: debugger\getoutputcallbacks.htm
tech.root: debugger
ms.assetid: 43f27e56-a6aa-4548-9c96-000e53a7eb9a
ms.date: 05/03/2018
keywords: ["IDebugClient2::GetOutputCallbacks"]
ms.keywords: GetOutputCallbacks, GetOutputCallbacks method [Windows Debugging], GetOutputCallbacks method [Windows Debugging],IDebugClient interface, GetOutputCallbacks method [Windows Debugging],IDebugClient2 interface, GetOutputCallbacks method [Windows Debugging],IDebugClient3 interface, GetOutputCallbacks method [Windows Debugging],IDebugClient4 interface, GetOutputCallbacks method [Windows Debugging],IDebugClient5 interface, IDebugClient interface [Windows Debugging],GetOutputCallbacks method, IDebugClient2 interface [Windows Debugging],GetOutputCallbacks method, IDebugClient2.GetOutputCallbacks, IDebugClient2::GetOutputCallbacks, IDebugClient3 interface [Windows Debugging],GetOutputCallbacks method, IDebugClient3::GetOutputCallbacks, IDebugClient4 interface [Windows Debugging],GetOutputCallbacks method, IDebugClient4::GetOutputCallbacks, IDebugClient5 interface [Windows Debugging],GetOutputCallbacks method, IDebugClient5::GetOutputCallbacks, IDebugClient::GetOutputCallbacks, IDebugClient_693aaf2a-8408-48c4-b7c0-66e7064a6f35.xml, dbgeng/IDebugClient2::GetOutputCallbacks, dbgeng/IDebugClient3::GetOutputCallbacks, dbgeng/IDebugClient4::GetOutputCallbacks, dbgeng/IDebugClient5::GetOutputCallbacks, dbgeng/IDebugClient::GetOutputCallbacks, debugger.getoutputcallbacks
f1_keywords:
 - "dbgeng/IDebugClient.GetOutputCallbacks"
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
- IDebugClient.GetOutputCallbacks
- IDebugClient2.GetOutputCallbacks
- IDebugClient3.GetOutputCallbacks
- IDebugClient4.GetOutputCallbacks
- IDebugClient5.GetOutputCallbacks
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient2::GetOutputCallbacks


## -description


The <b>GetOutputCallbacks</b> method returns the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-input-and-output">output callbacks</a> object registered with the client.


## -parameters




### -param Callbacks [out]

Receives an interface pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugoutputcallbacks">IDebugOutputCallbacks</a> object registered with the client.


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



Each client can have at most one <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugoutputcallbacks">IDebugOutputCallbacks</a> or <b>IDebugOutputCallbacksWide</b> object registered with it for output.

If no output callbacks object is registered with the client, the value of <i>Callbacks</i> will be set to <b>NULL</b>.

The <b>IDebugOutputCallbacks</b> interface extends the COM interface <b>IUnknown</b>.  Before returning the <b>IDebugOutputCallbacks</b> object specified by <i>Callbacks</i>, the engine calls its <b>IUnknown::AddRef</b> method.  When this object is no longer needed, its <b>IUnknown::Release</b> method should be called.

For more information about callbacks, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-callback-objects">Callbacks</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugoutputcallbacks">IDebugOutputCallbacks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-setoutputcallbacks">SetOutputCallbacks</a>
 

 

