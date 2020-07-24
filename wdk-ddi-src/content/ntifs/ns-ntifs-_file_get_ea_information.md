---
UID: NS:ntifs._FILE_GET_EA_INFORMATION
title: _FILE_GET_EA_INFORMATION (ntifs.h)
description: The FILE_GET_EA_INFORMATION structure is used to query for extended-attribute (EA) information.
old-location: ifsk\file_get_ea_information.htm
tech.root: ifsk
ms.assetid: 2abaf505-b890-43b6-a277-d930417bdcb8
ms.date: 04/16/2018
keywords: ["_FILE_GET_EA_INFORMATION structure"]
ms.keywords: "*PFILE_GET_EA_INFORMATION, FILE_GET_EA_INFORMATION, FILE_GET_EA_INFORMATION structure [Installable File System Drivers], PFILE_GET_EA_INFORMATION, PFILE_GET_EA_INFORMATION structure pointer [Installable File System Drivers], _FILE_GET_EA_INFORMATION, fileinformationstructures_42834ee3-151e-4844-bd66-a20775e364b4.xml, ifsk.file_get_ea_information, ntifs/FILE_GET_EA_INFORMATION, ntifs/PFILE_GET_EA_INFORMATION"
f1_keywords:
 - "ntifs/FILE_GET_EA_INFORMATION"
 - "FILE_GET_EA_INFORMATION"
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
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
- HeaderDef
api_location:
- ntifs.h
api_name:
- FILE_GET_EA_INFORMATION
targetos: Windows
req.typenames: FILE_GET_EA_INFORMATION, *PFILE_GET_EA_INFORMATION
---

# _FILE_GET_EA_INFORMATION structure


## -description


The FILE_GET_EA_INFORMATION structure is used to query for extended-attribute (EA) information. 


## -struct-fields




### -field NextEntryOffset

Offset, in bytes, of the next FILE_GET_EA_INFORMATION-typed entry. This member is zero if no other entries follow this one. 


### -field EaNameLength

Length, in bytes, of the <b>EaName</b> array. This value does not include a NULL terminator. 


### -field EaName

Specifies the first character of the name of the extended attribute to be queried. This is followed in memory by the remainder of the string. 


## -remarks



The FILE_GET_EA_INFORMATION structure is used to query for extended-attribute (EA) information. The EA information is returned in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_full_ea_information">FILE_FULL_EA_INFORMATION</a>-structured buffer. 

This structure must be aligned on a LONG (4-byte) boundary. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_full_ea_information">FILE_FULL_EA_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-ea">IRP_MJ_QUERY_EA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iocheckeabuffervalidity">IoCheckEaBufferValidity</a>
 

 

