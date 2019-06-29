---
UID: NS:ndis._NET_BUFFER_SHARED_MEMORY
title: _NET_BUFFER_SHARED_MEMORY (ndis.h)
description: The NET_BUFFER_SHARED_MEMORY structure specifies a shared memory buffer that is associated with a NET_BUFFER structure.
old-location: netvista\net_buffer_shared_memory.htm
tech.root: netvista
ms.assetid: 492bb1cd-fc3e-4e85-9074-32ebbf1fb837
ms.date: 05/02/2018
ms.keywords: "*PNET_BUFFER_SHARED_MEMORY, NET_BUFFER_SHARED_MEMORY, NET_BUFFER_SHARED_MEMORY structure [Network Drivers Starting with Windows Vista], PNET_BUFFER_SHARED_MEMORY, PNET_BUFFER_SHARED_MEMORY structure pointer [Network Drivers Starting with Windows Vista], _NET_BUFFER_SHARED_MEMORY, ndis/NET_BUFFER_SHARED_MEMORY, ndis/PNET_BUFFER_SHARED_MEMORY, ndis_netbuf_macros_media_specific_5b9066cf-413a-4483-9b05-e06ceed9081e.xml, netvista.net_buffer_shared_memory"
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
- ndis.h
api_name:
- NET_BUFFER_SHARED_MEMORY
product:
- Windows
targetos: Windows
req.typenames: NET_BUFFER_SHARED_MEMORY, *PNET_BUFFER_SHARED_MEMORY
---

# _NET_BUFFER_SHARED_MEMORY structure


## -description


The NET_BUFFER_SHARED_MEMORY structure specifies a shared memory buffer that is associated with a 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure.


## -struct-fields




### -field NextSharedMemorySegment

A pointer to the next NET_BUFFER_SHARED_MEMORY structure in a NULL-terminated linked list of such
     structures.


### -field SharedMemoryFlags

A ULONG value that contains shared memory flags. This member is reserved for future use.


### -field SharedMemoryHandle

An NDIS_HANDLE that contains an NDIS shared memory handle.


### -field SharedMemoryOffset

A ULONG value that contains the offset, in bytes, of the shared memory.


### -field SharedMemoryLength

A ULONG value for the length, in bytes, of the shared memory segment.


## -remarks



An NDIS 6.20 or later driver uses the NET_BUFFER_SHARED_MEMORY structure to describe a shared memory
    buffer. There can be a linked list of such shared memory buffers that are associated with a 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure. Virtual machine queue (VMQ)
    capable NICs use these shared memory buffers in the virtualization environment.

Use the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-shared-mem-next-segment">
    NET_BUFFER_SHARED_MEM_NEXT_SEGMENT</a>, 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-shared-mem-flags">NET_BUFFER_SHARED_MEM_FLAGS</a>, 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-shared-mem-handle">NET_BUFFER_SHARED_MEM_HANDLE</a>, 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-shared-mem-offset">NET_BUFFER_SHARED_MEM_OFFSET</a>,
    and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-shared-mem-length">
    NET_BUFFER_SHARED_MEM_LENGTH</a> macros to access the NET_BUFFER_SHARED_MEMORY in a NET_BUFFER
    structure. The 
    <b>SharedMemoryInfo</b> member of the NET_BUFFER structure contains the first NET_BUFFER_SHARED_MEMORY
    structure in the linked list.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-shared-mem-flags">NET_BUFFER_SHARED_MEM_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-shared-mem-handle">NET_BUFFER_SHARED_MEM_HANDLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-shared-mem-length">NET_BUFFER_SHARED_MEM_LENGTH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-shared-mem-next-segment">
   NET_BUFFER_SHARED_MEM_NEXT_SEGMENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-shared-mem-offset">NET_BUFFER_SHARED_MEM_OFFSET</a>
 

 

