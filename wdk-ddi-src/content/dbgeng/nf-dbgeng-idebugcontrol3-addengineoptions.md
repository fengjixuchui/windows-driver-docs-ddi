---
UID: NF:dbgeng.IDebugControl3.AddEngineOptions
title: IDebugControl3::AddEngineOptions (dbgeng.h)
description: The AddEngineOptions method turns on some of the debugger engine's options.
old-location: debugger\addengineoptions.htm
tech.root: debugger
ms.assetid: 088036f5-13cb-47ba-953c-a71c923f028e
ms.date: 05/03/2018
keywords: ["IDebugControl3::AddEngineOptions"]
ms.keywords: AddEngineOptions, AddEngineOptions method [Windows Debugging], AddEngineOptions method [Windows Debugging],IDebugControl interface, AddEngineOptions method [Windows Debugging],IDebugControl2 interface, AddEngineOptions method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],AddEngineOptions method, IDebugControl2 interface [Windows Debugging],AddEngineOptions method, IDebugControl2::AddEngineOptions, IDebugControl3 interface [Windows Debugging],AddEngineOptions method, IDebugControl3.AddEngineOptions, IDebugControl3::AddEngineOptions, IDebugControl::AddEngineOptions, IDebugControl_6042b0b9-8175-4790-be19-43f8659716dc.xml, dbgeng/IDebugControl2::AddEngineOptions, dbgeng/IDebugControl3::AddEngineOptions, dbgeng/IDebugControl::AddEngineOptions, debugger.addengineoptions
f1_keywords:
 - "dbgeng/IDebugControl.AddEngineOptions"
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
- Dbgeng.h
api_name:
- IDebugControl.AddEngineOptions
- IDebugControl2.AddEngineOptions
- IDebugControl3.AddEngineOptions
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::AddEngineOptions


## -description


The <b>AddEngineOptions</b> method turns on some of the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/introduction">debugger engine</a>'s options.


## -parameters




### -param Options [in]

Specifies engine options to turn on.  <i>Options</i> is a bit-set that will be combined with the existing engine options using the bitwise-OR operator.  For a description of the engine options, see <a href="https://docs.microsoft.com/previous-versions/ff541475(v=vs.85)">DEBUG_ENGOPT_XXX</a>.


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
 

This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.




## -remarks



After the engine options have been changed, the engine sends out notification to each client's <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/e">event callback object</a> by passing the DEBUG_CES_ENGINE_OPTIONS flag to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-changeenginestate">IDebugEventCallbacks::ChangeEngineState</a> method.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getengineoptions">GetEngineOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-removeengineoptions">RemoveEngineOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setengineoptions">SetEngineOptions</a>
 

 

