---
UID: NF:dbgeng.IDebugControl5.OutputStackTraceEx
title: IDebugControl5::OutputStackTraceEx (dbgeng.h)
description: The OutputStackTraceEx method outputs either the supplied stack frame or the current stack frames.
old-location: debugger\idebugcontrol5_outputstacktraceex.htm
tech.root: debugger
ms.assetid: C89203F9-FCCF-4D71-8E8A-9F5F4AE89004
ms.date: 05/03/2018
keywords: ["IDebugControl5::OutputStackTraceEx"]
ms.keywords: IDebugControl5 interface [Windows Debugging],OutputStackTraceEx method, IDebugControl5.OutputStackTraceEx, IDebugControl5::OutputStackTraceEx, OutputStackTraceEx, OutputStackTraceEx method [Windows Debugging], OutputStackTraceEx method [Windows Debugging],IDebugControl5 interface, dbgeng/IDebugControl5::OutputStackTraceEx, debugger.idebugcontrol5_outputstacktraceex
f1_keywords:
 - "dbgeng/IDebugControl5.OutputStackTraceEx"
 - "IDebugControl5.OutputStackTraceEx"
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
- IDebugControl5.OutputStackTraceEx
targetos: Windows
req.typenames: 
---

# IDebugControl5::OutputStackTraceEx


## -description


The OutputStackTraceEx method outputs either the supplied stack frame or the current stack frames.   The OutputStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debugging-optimized-code-and-inline-functions-external">Debugging Optimized Code and Inline Functions</a>.


## -parameters




### -param OutputControl [in]

Specifies where to send the output.  For possible values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-outctl-xxx">DEBUG_OUTCTL_XXX</a>.


### -param Frames [in, optional]

Specifies the array of stack frames to output.  The number of elements in this array is <i>FramesSize</i>.  If <i>Frames</i> is <b>NULL</b>, the current stack frames are used.


### -param FramesSize [in]

Specifies the number of frames to output.


### -param Flags [in]

Specifies bit flags that determine what information to output for each frame.  <i>Flags</i> can be any combination of values from the following table.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_STACK_ARGUMENTS

</td>
<td>
Displays the first three pieces of stack memory at the frame of each call.  On platforms where parameters are passed on the stack, and the code for the frame uses stack arguments, these values will be the arguments to the function.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_FUNCTION_INFO

</td>
<td>
Displays information about the function that corresponds to the frame.  This includes calling convention and frame pointer omission (FPO) information.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_SOURCE_LINE

</td>
<td>
Displays source line information for each frame of the stack trace.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_FRAME_ADDRESSES

</td>
<td>
Displays the return address, previous frame address, and other relevant addresses for each frame.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_COLUMN_NAMES

</td>
<td>
Displays column names.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_NONVOLATILE_REGISTERS

</td>
<td>
Displays the non-volatile register context for each frame.  This is only meaningful for some platforms.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_FRAME_NUMBERS

</td>
<td>
Displays frame numbers.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_PARAMETERS

</td>
<td>
Displays parameter names and values as given in symbol information.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_FRAME_ADDRESSES_RA_ONLY

</td>
<td>
Displays just the return address in stack frame addresses.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_FRAME_MEMORY_USAGE

</td>
<td>
Displays the number of bytes that separate the frames.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_PARAMETERS_NEWLINE

</td>
<td>
Displays each parameter and its type and value on a new line.

</td>
</tr>
</table>
 


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



The array of stack frames can be obtained using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol5-getstacktraceex">GetStackTraceEx</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol5-getcontextstacktraceex">GetContextStackTraceEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol5-getstacktraceex">GetStackTraceEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol5">IDebugControl5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/k--kb--kc--kd--kp--kp--kv--display-stack-backtrace-">k, kb, kc, kd, kp, kP, kv (Display Stack Backtrace)</a>
 

 

