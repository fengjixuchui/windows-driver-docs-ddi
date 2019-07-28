---
UID: NF:dbgeng.IDebugControl3.CallExtension
title: IDebugControl3::CallExtension (dbgeng.h)
description: The CallExtension method calls a debugger extension.
old-location: debugger\callextension.htm
tech.root: debugger
ms.assetid: 0d0f23db-5eef-486a-a393-dd3b37826f48
ms.date: 05/03/2018
ms.keywords: CallExtension, CallExtension method [Windows Debugging], CallExtension method [Windows Debugging],IDebugControl interface, CallExtension method [Windows Debugging],IDebugControl2 interface, CallExtension method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],CallExtension method, IDebugControl2 interface [Windows Debugging],CallExtension method, IDebugControl2::CallExtension, IDebugControl3 interface [Windows Debugging],CallExtension method, IDebugControl3.CallExtension, IDebugControl3::CallExtension, IDebugControl::CallExtension, IDebugControl_c37b420a-b94b-4d54-8a5a-2e1a74b49f26.xml, dbgeng/IDebugControl2::CallExtension, dbgeng/IDebugControl3::CallExtension, dbgeng/IDebugControl::CallExtension, debugger.callextension
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugControl.CallExtension"
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
- IDebugControl.CallExtension
- IDebugControl2.CallExtension
- IDebugControl3.CallExtension
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::CallExtension


## -description


The <b>CallExtension</b> method calls a debugger extension.


## -parameters




### -param Handle [in]

Specifies the handle of the extension library that contains the extension to call.  If <i>Handle</i> is zero, the engine will walk the extension library chain searching for the extension.


### -param Function [in]

Specifies the name of the extension to call.


### -param Arguments [in, optional]

Specifies the arguments to pass to the extension.  <i>Arguments</i> is a string that will be parsed by the extension, just like the extension will parse arguments passed to it when called as an extension command.


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
 

This method can also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.




## -remarks



If <i>Handle</i> is zero, the engine searches each extension library until it finds one that contains the extension; the extension will then be called.  If the extension returns DEBUG_EXTENSION_CONTINUE_SEARCH, the search will continue.

For more information on using extension libraries, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/calling-extensions-and-extension-functions">Calling Extensions and Extension Functions</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-addextension">AddExtension</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getextensionbypath">GetExtensionByPath</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getextensionfunction">GetExtensionFunction</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>
 

 

