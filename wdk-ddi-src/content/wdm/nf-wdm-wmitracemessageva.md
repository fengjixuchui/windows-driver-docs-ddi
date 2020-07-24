---
UID: NF:wdm.WmiTraceMessageVa
title: WmiTraceMessageVa function (wdm.h)
description: The WmiTraceMessageVa routine adds a message to the output log of a WPP software tracing session.
old-location: kernel\wmitracemessageva.htm
tech.root: kernel
ms.assetid: 57f8006c-defe-4975-9d21-0eaecae5a873
ms.date: 04/30/2018
keywords: ["WmiTraceMessageVa function"]
ms.keywords: WmiTraceMessageVa, WmiTraceMessageVa routine [Kernel-Mode Driver Architecture], k902_c9c7dd80-d7a8-4b53-bcf1-f64c822e9e6d.xml, kernel.wmitracemessageva, wdm/WmiTraceMessageVa
f1_keywords:
 - "wdm/WmiTraceMessageVa"
 - "WmiTraceMessageVa"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- WmiTraceMessageVa
targetos: Windows
req.typenames: 
---

# WmiTraceMessageVa function


## -description


The <b>WmiTraceMessageVa</b> routine adds a message to the output log of a <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/wpp-software-tracing">WPP software tracing</a> session.


## -parameters




### -param LoggerHandle [in]

Specifies a trace handle for a software tracing session.


### -param MessageFlags [in]

Specifies a bitwise OR of one or more message flags. See the Remarks section for details.


### -param MessageGuid [in]

Specifies a GUID that identifies a software trace class.


### -param MessageNumber [in]

Identifies the message subtype. The meaning of subtypes is specific to the software trace class and the provider. 


### -param MessageArgList [in]

Provides a required list of message parameters that specify a set of message parts. The parameters are organized as a sequence of parameter pairs, where each pair specifies one part of the complete message. Each parameter pair consists of a PVOID pointer to data, followed immediately by a ULONG value that specifies the length of the data. The parameter list must be terminated by a <b>NULL</b> PVOID pointer followed by a ULONG(0). 


## -returns



<b>WmiTraceMessageVa</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
<i>LoggerHandle</i> is not a valid software trace handle.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
There is insufficient buffer memory to log the message. See the Remarks section for more information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other NTSTATUS value</b></dt>
</dl>
</td>
<td width="60%">
An internal error occurred.

</td>
</tr>
</table>
 




## -remarks



A caller can use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-wmitracemessage">WmiTraceMessage</a> or <b>WmiTraceMessageVa</b> to add a message to the output log of a WPP software tracing session. <b>WmiTraceMessage</b> simplifies a caller's code by handling the variable list mechanism before calling <b>WmiTraceMessageVa</b>.

A caller can set the following message flags:

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
TRACE_MESSAGE_SEQUENCE

</td>
<td>
Include a sequence number in the message. Message sequencing can only be used if it is enabled for the software tracing session specified by <i>LoggerHandle</i>.

</td>
</tr>
<tr>
<td>
TRACE_MESSAGE_GUID

</td>
<td>
<i>MessageGuid</i> specifies a GUID that identifies a software trace class. This flag must be set.

</td>
</tr>
<tr>
<td>
TRACE_MESSAGE_TIMESTAMP

</td>
<td>
Include a time stamp in the message.

</td>
</tr>
<tr>
<td>
TRACE_MESSAGE_PERFORMANCE_TIMESTAMP

</td>
<td>
This flag is not implemented and is <u>obsolete</u>. It must not be used. 

</td>
</tr>
<tr>
<td>
TRACE_MESSAGE_SYSTEMINFO

</td>
<td>
Include the thread identifier (TID) and process identifier (PID) in the message.

</td>
</tr>
</table>
 

<b>WmiTraceMessageVa</b> does not log the message if one of the following is true:

<ul>
<li>
The total size, in bytes, of the message data and the message header is greater than the size of individual message buffers allocated for a software tracing session. (The maximum message header size is 48 bytes.)

</li>
<li>
All message buffers allocated to software tracing session are full. 

</li>
</ul>
<b>WmiTraceMessageVa</b> runs at the IRQL of the caller.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiwriteevent">IoWmiWriteEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_trace_information_class">TRACE_INFORMATION_CLASS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmilib/nf-wmilib-wmifireevent">WmiFireEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-wmiquerytraceinformation">WmiQueryTraceInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-wmitracemessage">WmiTraceMessage</a>
 

 

