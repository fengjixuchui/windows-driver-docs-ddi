---
UID: NS:ntifs._FILE_PIPE_INFORMATION
title: _FILE_PIPE_INFORMATION (ntifs.h)
description: The FILE_PIPE_INFORMATION structure contains information about a named pipe that is not specific to the local or the remote end of the pipe.
old-location: ifsk\file_pipe_information.htm
tech.root: ifsk
ms.assetid: d38b9f36-27f1-47f1-a469-18ddb6f5b2c1
ms.date: 04/16/2018
keywords: ["_FILE_PIPE_INFORMATION structure"]
ms.keywords: "*PFILE_PIPE_INFORMATION, FILE_PIPE_INFORMATION, FILE_PIPE_INFORMATION structure [Installable File System Drivers], PFILE_PIPE_INFORMATION, PFILE_PIPE_INFORMATION structure pointer [Installable File System Drivers], _FILE_PIPE_INFORMATION, ifsk.file_pipe_information, ntifs/FILE_PIPE_INFORMATION, ntifs/PFILE_PIPE_INFORMATION"
f1_keywords:
 - "ntifs/FILE_PIPE_INFORMATION"
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating system.
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
- HeaderDef
api_location:
- ntifs.h
api_name:
- FILE_PIPE_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: FILE_PIPE_INFORMATION, *PFILE_PIPE_INFORMATION
---

# _FILE_PIPE_INFORMATION structure


## -description


The <b>FILE_PIPE_INFORMATION</b> structure contains information about a named pipe that is not specific to the local or the remote end of the pipe.


## -struct-fields




### -field ReadMode

One of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>FILE_PIPE_BYTE_STREAM_MODE
(0x00000000)</td>
<td>Data is read from the pipe as a stream of bytes.</td>
</tr>
<tr>
<td>FILE_PIPE_MESSAGE_MODE
(0x00000001)</td>
<td>Data is read from the pipe as a stream of messages.</td>
</tr>
</table>
 


### -field CompletionMode

One of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>FILE_PIPE_QUEUE_OPERATION
(0x00000000)</td>
<td>Blocking mode</td>
</tr>
<tr>
<td>FILE_PIPE_COMPLETE_OPERATION
(0x00000001)</td>
<td>Non-blocking mode </td>
</tr>
</table>
 


## -remarks



If <b>ReadMode</b> is set to FILE_PIPE_BYTE_STREAM_MODE, any attempt to change it must fail with a STATUS_INVALID_PARAMETER error code.

When <b>CompletionMode</b> is set to FILE_PIPE_QUEUE_OPERATION, if the pipe is connected to, read to, or written from, the operation is not completed until there is data to read, all data is written, or a client is connected. 

<div class="alert"><b>Note</b>  A value of FILE_PIPE_QUEUE_OPERATION for <b>CompletionMode</b> can result in waiting indefinitely for a client process to perform an action.</div>
<div> </div>
When <b>CompletionMode</b> is set to FILE_PIPE_COMPLETE_OPERATION, if the pipe is being connected to, read to, or written from, the operation is completed immediately. 

For information about pipes, see <a href="https://docs.microsoft.com/windows/desktop/ipc/pipes">Pipes</a>.



