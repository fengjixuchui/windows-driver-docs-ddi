---
UID: NS:ntifs._NFS_OPEN_ECP_CONTEXT
title: _NFS_OPEN_ECP_CONTEXT (ntifs.h)
description: The NFS_OPEN_ECP_CONTEXT structure is used by the Network File System (NFS) server to open files in response to client requests.
old-location: ifsk\nfs_open_ecp_context.htm
tech.root: ifsk
ms.assetid: f3600dca-d246-41b5-99b4-4054e677b03b
ms.date: 04/16/2018
keywords: ["_NFS_OPEN_ECP_CONTEXT structure"]
ms.keywords: "*PNFS_OPEN_ECP_CONTEXT, ECP_Structures_d19b2618-0b21-424c-b5bd-abc9b6bdc518.xml, NFS_OPEN_ECP_CONTEXT, NFS_OPEN_ECP_CONTEXT structure [Installable File System Drivers], PNFS_OPEN_ECP_CONTEXT, PNFS_OPEN_ECP_CONTEXT structure pointer [Installable File System Drivers], PPNFS_OPEN_ECP_CONTEXT, PPNFS_OPEN_ECP_CONTEXT structure pointer [Installable File System Drivers], _NFS_OPEN_ECP_CONTEXT, ifsk.nfs_open_ecp_context, ntifs/NFS_OPEN_ECP_CONTEXT, ntifs/PNFS_OPEN_ECP_CONTEXT, ntifs/PPNFS_OPEN_ECP_CONTEXT"
f1_keywords:
 - "ntifs/NFS_OPEN_ECP_CONTEXT"
 - "NFS_OPEN_ECP_CONTEXT"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting with Windows 7.
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
- NFS_OPEN_ECP_CONTEXT
targetos: Windows
req.typenames: NFS_OPEN_ECP_CONTEXT, *PNFS_OPEN_ECP_CONTEXT, PPNFS_OPEN_ECP_CONTEXT
---

# _NFS_OPEN_ECP_CONTEXT structure


## -description


The NFS_OPEN_ECP_CONTEXT structure is used by the Network File System (NFS) server to open files in response to client requests. 


## -struct-fields




### -field ExportAlias

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that supplies the export alias (share name) for the NFS server that contains the files to be opened. This member is a hint and can be a name, <b>NULL</b>, or a zero-length string. 


### -field ClientSocketAddress

A pointer to a <a href="https://docs.microsoft.com/windows/win32/api/ws2def/ns-ws2def-sockaddr_storage_lh">SOCKADDR_STORAGE</a> structure that specifies the transport address of the client computer. This client originates the open file request. 


## -remarks



The file-system stack can determine whether NFS_OPEN_ECP_CONTEXT is attached to the create file request. The file-system stack can then use the information in NFS_OPEN_ECP_CONTEXT to determine the client that requested that the file be opened and why it was requested. For information about how to retrieve the NFS_OPEN_ECP_CONTEXT extra information that is attached to a create file request, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/using-ecps-to-process-irp-mj-create-operations-in-a-file-system-filter">Retrieving ECPs</a>. 

The NFS_OPEN_ECP_CONTEXT structure is read-only. You should use it to retrieve information about the open file ECP only. For more information about this issue, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/system-defined-ecps">System-Defined ECPs</a>.




## -see-also




<a href="https://docs.microsoft.com/windows/win32/api/ws2def/ns-ws2def-sockaddr_storage_lh">SOCKADDR_STORAGE</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

