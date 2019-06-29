---
UID: NF:dbgeng.IDebugControl4.GetPromptTextWide
title: IDebugControl4::GetPromptTextWide (dbgeng.h)
description: The GetPromptTextWide method returns the standard prompt text that will be prepended to the formatted output specified in the OutputPrompt and OutputPromptVaList methods.
old-location: debugger\getprompttextwide.htm
tech.root: debugger
ms.assetid: 10d5da82-8fbe-45fa-8051-42f6a1e3adce
ms.date: 05/03/2018
ms.keywords: GetPromptTextWide, GetPromptTextWide method [Windows Debugging], GetPromptTextWide method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],GetPromptTextWide method, IDebugControl4.GetPromptTextWide, IDebugControl4::GetPromptTextWide, dbgeng/IDebugControl4::GetPromptTextWide, debugger.getprompttextwide
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
- IDebugControl4.GetPromptTextWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::GetPromptTextWide


## -description


The <b>GetPromptTextWide</b>  method returns the standard prompt text that will be prepended to the formatted output specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553227">OutputPrompt</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-outputpromptvalist">OutputPromptVaList</a> methods.


## -parameters




### -param Buffer [out, optional]

Receives the prompt text.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size, in characters, of the <i>Buffer</i> buffer.


### -param TextSize [out, optional]

Receives the size, in characters, of the prompt text.  If <i>TextSize</i> is <b>NULL</b>, this information is not returned.


## -returns



This method can also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.  However, the prompt text was too large to fit into the <i>Buffer</i> buffer and the text was truncated.

</td>
</tr>
</table>
 




## -remarks



For more information about prompting the user, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-input-and-output">Using Input and Output</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553227">OutputPrompt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-outputpromptvalist">OutputPromptVaList</a>
 

 

