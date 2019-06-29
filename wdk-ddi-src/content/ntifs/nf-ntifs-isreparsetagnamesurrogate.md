---
UID: NF:ntifs.IsReparseTagNameSurrogate
title: IsReparseTagNameSurrogate macro (ntifs.h)
description: The IsReparseTagNameSurrogate macro determines whether a tag's associated reparse point is a surrogate for another named entity, such as a volume mount point.
old-location: ifsk\isreparsetagnamesurrogate.htm
tech.root: ifsk
ms.assetid: 51e80cd6-19c1-4e21-b676-662c77840a8b
ms.date: 04/16/2018
ms.keywords: IsReparseTagNameSurrogate, IsReparseTagNameSurrogate function [Installable File System Drivers], ifsk.isreparsetagnamesurrogate, ioref_f44ef76c-2211-43a1-b151-a5804c7cd361.xml, ntifs/IsReparseTagNameSurrogate
ms.topic: macro
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- IsReparseTagNameSurrogate
product:
- Windows
targetos: Windows
req.typenames: 
---

# IsReparseTagNameSurrogate macro


## -description


The <b>IsReparseTagNameSurrogate</b> macro determines whether a tag's associated reparse point is a surrogate for another named entity, such as a volume mount point. 


## -parameters




### -param _tag [in]

Reparse point tag to be tested. 


## -remarks



If the name surrogate bit is set in the reparse tag, the file or directory represents another named entity in the system, such as a volume mount point. 

For more information about reparse points and volume mount points, see the Microsoft Windows SDK documentation. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-delete-reparse-point">FSCTL_DELETE_REPARSE_POINT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-get-reparse-point">FSCTL_GET_REPARSE_POINT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-set-reparse-point">FSCTL_SET_REPARSE_POINT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltfscontrolfile">FltFsControlFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-flttagfile">FltTagFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltuntagfile">FltUntagFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-isreparsetagmicrosoft">IsReparseTagMicrosoft</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_reparse_data_buffer">REPARSE_DATA_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_reparse_guid_data_buffer">REPARSE_GUID_DATA_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566462">ZwFsControlFile</a>
 

 

