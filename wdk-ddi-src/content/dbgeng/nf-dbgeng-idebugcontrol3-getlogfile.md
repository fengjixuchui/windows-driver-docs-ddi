---
UID: NF:dbgeng.IDebugControl3.GetLogFile
title: IDebugControl3::GetLogFile (dbgeng.h)
description: The GetLogFile method returns the name of the currently open log file.
old-location: debugger\getlogfile.htm
tech.root: debugger
ms.assetid: 9d71a817-55b5-4042-8de8-15b23e51dffd
ms.date: 05/03/2018
keywords: ["IDebugControl3::GetLogFile"]
ms.keywords: GetLogFile, GetLogFile method [Windows Debugging], GetLogFile method [Windows Debugging],IDebugControl interface, GetLogFile method [Windows Debugging],IDebugControl2 interface, GetLogFile method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetLogFile method, IDebugControl2 interface [Windows Debugging],GetLogFile method, IDebugControl2::GetLogFile, IDebugControl3 interface [Windows Debugging],GetLogFile method, IDebugControl3.GetLogFile, IDebugControl3::GetLogFile, IDebugControl::GetLogFile, IDebugControl_cad2fa56-b2ca-4a26-822e-193acf602913.xml, dbgeng/IDebugControl2::GetLogFile, dbgeng/IDebugControl3::GetLogFile, dbgeng/IDebugControl::GetLogFile, debugger.getlogfile
f1_keywords:
 - "dbgeng/IDebugControl.GetLogFile"
 - "IDebugControl.GetLogFile"
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
- IDebugControl.GetLogFile
- IDebugControl2.GetLogFile
- IDebugControl3.GetLogFile
targetos: Windows
req.typenames: 
---

# IDebugControl3::GetLogFile


## -description


The <b>GetLogFile</b>  method returns the name of the currently open log file.


## -parameters




### -param Buffer [out, optional]

Receives the name of the currently open log file.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size, in characters, of the <i>Buffer</i> buffer.


### -param FileSize [out, optional]

Receives the size, in characters, of the name of the log file.  If <i>FileSize</i> is <b>NULL</b>, this information is not returned.


### -param Append [out]

Receives <b>TRUE</b> if log messages are appended to the log file, or <b>FALSE</b> if the contents of the log file were discarded when the file was opened.


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



<b>GetLogFile</b> and <b>GetLogFileWide</b> behave the same way as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol4-getlogfile2">GetLogFile2</a> and <b>GetLogFile2Wide</b> with <i>Append</i> receiving only the information about the DEBUG_LOG_APPEND flag.

For more information about log files, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-input-and-output">Using Input and Output</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-closelogfile">CloseLogFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol4-getlogfile2">GetLogFile2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getlogmask">GetLogMask</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-openlogfile">OpenLogFile</a>
 

 

