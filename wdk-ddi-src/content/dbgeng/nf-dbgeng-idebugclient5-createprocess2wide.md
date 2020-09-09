---
UID: NF:dbgeng.IDebugClient5.CreateProcess2Wide
title: IDebugClient5::CreateProcess2Wide (dbgeng.h)
description: The CreateProcess2Wide method executes the specified command to create a new process.
old-location: debugger\createprocess2wide.htm
tech.root: debugger
ms.assetid: b032ca68-5ac5-4a19-84fe-92058905a1d7
ms.date: 05/03/2018
keywords: ["IDebugClient5::CreateProcess2Wide"]
ms.keywords: CreateProcess2Wide, CreateProcess2Wide method [Windows Debugging], CreateProcess2Wide method [Windows Debugging],IDebugClient5 interface, IDebugClient5 interface [Windows Debugging],CreateProcess2Wide method, IDebugClient5.CreateProcess2Wide, IDebugClient5::CreateProcess2Wide, dbgeng/IDebugClient5::CreateProcess2Wide, debugger.createprocess2wide
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
 - IDebugClient5::CreateProcess2Wide
 - dbgeng/IDebugClient5::CreateProcess2Wide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient5.CreateProcess2Wide
---

# IDebugClient5::CreateProcess2Wide


## -description

The <b>CreateProcess2Wide</b> method executes the specified command to create a new process.

## -parameters

### -param Server 

[in]
Specifies the process server that will be attached to the process.  If <i>Server</i> is zero, the engine will create the local process without using a process server.

### -param CommandLine 

[in]
Specifies the command line to execute to create the new process.

### -param OptionsBuffer 

[in]
Specifies the process creation options.  <i>OptionsBuffer</i> is a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_create_process_options">DEBUG_CREATE_PROCESS_OPTIONS</a> structure.

### -param OptionsBufferSize 

[in]
Specifies the size of the buffer <i>OptionsBuffer</i>.  This should be set to <b>sizeof(DEBUG_CREATE_PROCESS_OPTIONS)</b>.

### -param InitialDirectory 

[in, optional]
Specifies the starting directory for the process.  If <i>InitialDirectory</i> is <b>NULL</b>, the current directory for the process server is used.

### -param Environment 

[in, optional]
Specifies an environment block for the new process.  An environment block consists of a null-terminated block of null-terminated strings.  Each string is of the form:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>name=value</pre>
</td>
</tr>
</table></span></div>
Note that the last two characters of the environment block are both <b>NULL</b>: one to terminate the string and one to terminate the block.

If <i>Environment</i> is set to <b>NULL</b>, the new process inherits the environment block of the process server.  If the DEBUG_CREATE_PROCESS_THROUGH_RTL flag is set in <i>OptionsBuffer</i>, then <i>Environment</i> must be <b>NULL</b>.

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

This method is available only for live user-mode debugging.

If <i>CreateFlags</i> contains either of the flags DEBUG_PROCESS or DEBUG_ONLY_THIS_PROCESS, the engine will also attach to the newly created process. This is similar to the behavior of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-createprocessandattach2">CreateProcessAndAttach2</a> with its argument <i>ProcessId</i> set to zero.

For more information about creating and attaching to live user-mode targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/live-user-mode-targets">Live User-Mode Targets</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-create--create-process-">.create (Create Process)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-abandoncurrentprocess">AbandonCurrentProcess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-attachprocess">AttachProcess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-connectprocessserver">ConnectProcessServer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-createprocess2">CreateProcess2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-createprocessandattach2">CreateProcessAndAttach2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-detachcurrentprocess">DetachCurrentProcess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getrunningprocessdescription">GetRunningProcessDescription</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getrunningprocesssystemids">GetRunningProcessSystemIds</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-terminatecurrentprocess">TerminateCurrentProcess</a>

