---
UID: NF:dbgeng.IDebugRegisters2.SetPseudoValues
title: IDebugRegisters2::SetPseudoValues (dbgeng.h)
description: The SetPseudoValues method sets the value of several pseudo-registers.
old-location: debugger\setpseudovalues.htm
tech.root: debugger
ms.assetid: 89bfe36a-6674-43b7-a889-24fe15771aea
ms.date: 05/03/2018
keywords: ["IDebugRegisters2::SetPseudoValues"]
ms.keywords: IDebugRegisters2 interface [Windows Debugging],SetPseudoValues method, IDebugRegisters2.SetPseudoValues, IDebugRegisters2::SetPseudoValues, IDebugRegisters_db4bc070-c017-479f-b9ca-4b2abe513d7f.xml, SetPseudoValues, SetPseudoValues method [Windows Debugging], SetPseudoValues method [Windows Debugging],IDebugRegisters2 interface, dbgeng/IDebugRegisters2::SetPseudoValues, debugger.setpseudovalues
f1_keywords:
 - "dbgeng/IDebugRegisters2.SetPseudoValues"
 - "IDebugRegisters2.SetPseudoValues"
req.header: dbgeng.h
req.include-header: DbgEng.h
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
- IDebugRegisters2.SetPseudoValues
targetos: Windows
req.typenames: 
---

# IDebugRegisters2::SetPseudoValues


## -description


The <b>SetPseudoValues</b> method sets the value of several pseudo-registers.


## -parameters




### -param Source [in]

Specifies the register source to query.

The possible values are listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Register source</th>
</tr>
<tr>
<td>
DEBUG_REGSRC_DEBUGGEE

</td>
<td>
Fetch register information from the target.

</td>
</tr>
<tr>
<td>
DEBUG_REGSRC_EXPLICIT

</td>
<td>
Fetch register information from the current explicit <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/changing-contexts">register context</a>.

</td>
</tr>
<tr>
<td>
DEBUG_REGSRC_FRAME

</td>
<td>
Fetch register information from the current scope's register context.

<div class="alert"><b>Note</b>    Stack unwinding does not guarantee accurate updating of the register context, so the scope frame's register context might not be accurate in all cases.</div>
<div> </div>
</td>
</tr>
</table>
 


### -param Count [in]

Specifies the number of pseudo-registers whose values are being set.


### -param Indices [in, optional]

Specifies an array of indices of pseudo-registers.  These are the pseudo-registers whose values will be set.  The size of <i>Indices</i> is <i>Count</i>.  If <i>Indices</i> is <b>NULL</b>, <i>Start</i> is used to specify the indices instead.


### -param Start [in]

Specifies the index of the first pseudo-register whose value will be set.  The pseudo-registers with indices between <i>Start</i> and <i>Start</i> plus <i>Count</i> minus one, will be set.  <i>Start</i> is only used if <i>Indices</i> is <b>NULL</b>.


### -param Values [in]

Specifies the new values of the pseudo-registers.  The number of elements this array holds is <i>Count</i>.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_value">DEBUG_VALUE</a> for a description of this parameter type.


## -returns



This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">HRESULT Values</a>.

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



For an overview of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters">IDebugRegisters</a> interface and other register-related methods, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/registers">Registers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugregisters2-getpseudovalues">GetPseudoValues</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters2">IDebugRegisters2</a>
 

 

