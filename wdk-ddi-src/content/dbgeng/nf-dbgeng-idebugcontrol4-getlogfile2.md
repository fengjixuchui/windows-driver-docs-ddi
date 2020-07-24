---
UID: NF:dbgeng.IDebugControl4.GetLogFile2
title: IDebugControl4::GetLogFile2 (dbgeng.h)
description: The GetLogFile2 method returns the name of the currently open log file.
old-location: debugger\getlogfile2.htm
tech.root: debugger
ms.assetid: 77ab08ce-96c5-4330-aab2-1bf4ab23cfc4
ms.date: 05/03/2018
keywords: ["IDebugControl4::GetLogFile2"]
ms.keywords: GetLogFile2, GetLogFile2 method [Windows Debugging], GetLogFile2 method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],GetLogFile2 method, IDebugControl4.GetLogFile2, IDebugControl4::GetLogFile2, IDebugControl_9822bd84-b8ee-4d36-a66f-e38567d23646.xml, dbgeng/IDebugControl4::GetLogFile2, debugger.getlogfile2
f1_keywords:
 - "dbgeng/IDebugControl4.GetLogFile2"
 - "IDebugControl4.GetLogFile2"
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
- IDebugControl4.GetLogFile2
targetos: Windows
req.typenames: 
---

# IDebugControl4::GetLogFile2


## -description


The <b>GetLogFile2</b>  method returns the name of the currently open log file.


## -parameters




### -param Buffer [out, optional]

Receives the name of the currently open log file.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size, in characters, of the <i>Buffer</i> buffer.


### -param FileSize [out, optional]

Receives the size, in characters, of the name of the log file.  If <i>FileSize</i> is <b>NULL</b>, this information is not returned.


### -param Flags [out]

Receives the bit-flags that were used when opening the log file.  See the <i>Flags</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol4-openlogfile2">OpenLogFile2</a> for a description of these flags.


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
The method was successful.  However, the name of the log file was too long to fit in the <i>Buffer</i> buffer so the name was truncated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
There is no currently open log file.

</td>
</tr>
</table>
 




## -remarks



For more information about log files, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-input-and-output">Using Input and Output</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-closelogfile">CloseLogFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getlogfile">GetLogFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getlogmask">GetLogMask</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol4-openlogfile2">OpenLogFile2</a>
 

 

