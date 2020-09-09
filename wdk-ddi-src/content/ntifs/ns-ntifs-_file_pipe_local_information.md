---
UID: NS:ntifs._FILE_PIPE_LOCAL_INFORMATION
title: _FILE_PIPE_LOCAL_INFORMATION (ntifs.h)
description: The FILE_PIPE_LOCAL_INFORMATION structure contains information about the local end of a named pipe.
old-location: ifsk\file_pipe_local_information.htm
tech.root: ifsk
ms.assetid: 7ca66b75-e5ff-46a6-8a40-47aa53bf0f6f
ms.date: 04/16/2018
keywords: ["FILE_PIPE_LOCAL_INFORMATION structure"]
ms.keywords: "*PFILE_PIPE_LOCAL_INFORMATION, FILE_PIPE_LOCAL_INFORMATION, FILE_PIPE_LOCAL_INFORMATION structure [Installable File System Drivers], PFILE_PIPE_LOCAL_INFORMATION, PFILE_PIPE_LOCAL_INFORMATION structure pointer [Installable File System Drivers], _FILE_PIPE_LOCAL_INFORMATION, ifsk.file_pipe_local_information, ntifs/FILE_PIPE_LOCAL_INFORMATION, ntifs/PFILE_PIPE_LOCAL_INFORMATION"
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
targetos: Windows
req.typenames: FILE_PIPE_LOCAL_INFORMATION, *PFILE_PIPE_LOCAL_INFORMATION
f1_keywords:
 - _FILE_PIPE_LOCAL_INFORMATION
 - ntifs/_FILE_PIPE_LOCAL_INFORMATION
 - PFILE_PIPE_LOCAL_INFORMATION
 - ntifs/PFILE_PIPE_LOCAL_INFORMATION
 - FILE_PIPE_LOCAL_INFORMATION
 - ntifs/FILE_PIPE_LOCAL_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FILE_PIPE_LOCAL_INFORMATION
---

# _FILE_PIPE_LOCAL_INFORMATION structure


## -description

The <b>FILE_PIPE_LOCAL_INFORMATION</b> structure contains information about the local end of a named pipe.

## -struct-fields

### -field NamedPipeType

One of the following named pipe types. 

<table>
<tr>
<th>Value </th>
<th>Meaning </th>
</tr>
<tr>
<td>FILE_PIPE_BYTE_STREAM_TYPE (0x00000000)</td>
<td>Data is read from the pipe as a stream of bytes.</td>
</tr>
<tr>
<td>FILE_PIPE_MESSAGE_TYPE (0x00000001)</td>
<td>Data is read from the pipe as a stream of messages.</td>
</tr>
</table>

### -field NamedPipeConfiguration

One of the following named pipe configurations.


<table>
<tr>
<th>Value </th>
<th>Meaning </th>
</tr>
<tr>
<td>FILE_PIPE_INBOUND
(0x00000000)
</td>
<td>The flow of data in the pipe goes from client to server only.</td>
</tr>
<tr>
<td>FILE_PIPE_OUTBOUND
(0x00000001)
</td>
<td>The flow of data in the pipe goes from server to client only.</td>
</tr>
<tr>
<td>FILE_PIPE_FULL_DUPLEX
(0x00000002)
</td>
<td>The pipe is bidirectional; both server and client processes can read from and write to the pipe. </td>
</tr>
</table>

### -field MaximumInstances

The maximum number of instances that can be created for this pipe. The first instance of the pipe must specify this value.

### -field CurrentInstances

The number of current named pipe instances.

### -field InboundQuota

 
The inbound quota, in bytes, for the named pipe.

### -field ReadDataAvailable

The amount of data available, in bytes, to be read from the named pipe.

### -field OutboundQuota

The outbound quota, in bytes, for the named pipe.

### -field WriteQuotaAvailable

The write quota, in bytes, for the named pipe.

### -field NamedPipeState

The connection status for the named pipe. This state has one of the following values.

<table>
<tr>
<th>Value </th>
<th>Meaning </th>
</tr>
<tr>
<td>FILE_PIPE_DISCONNECTED_STATE
(0x00000001)
</td>
<td>Named pipe is disconnected.</td>
</tr>
<tr>
<td>FILE_PIPE_LISTENING_STATE
(0x00000002)</td>
<td>Named pipe is waiting to establish a connection.</td>
</tr>
<tr>
<td>FILE_PIPE_CONNECTED_STATE
(0x00000003)</td>
<td>Named pipe is connected.</td>
</tr>
<tr>
<td>FILE_PIPE_CLOSING_STATE
(0x00000004)</td>
<td>Named pipe is in the process of being closed.</td>
</tr>
</table>

### -field NamedPipeEnd

The type of the named pipe end, which specifies whether this is the client or the server side of a named pipe.

<table>
<tr>
<th>Value </th>
<th>Meaning </th>
</tr>
<tr>
<td>FILE_PIPE_CLIENT_END
(0x00000000)</td>
<td>This is the client end of a named pipe.</td>
</tr>
<tr>
<td>FILE_PIPE_SERVER_END
(0x00000001)</td>
<td>This is the server end of a named pipe.</td>
</tr>
</table>

## -remarks

For information about pipes, see <a href="https://docs.microsoft.com/windows/desktop/ipc/pipes">Pipes</a>.

