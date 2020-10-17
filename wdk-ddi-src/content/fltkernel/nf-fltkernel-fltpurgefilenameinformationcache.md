---
UID: NF:fltkernel.FltPurgeFileNameInformationCache
title: FltPurgeFileNameInformationCache function (fltkernel.h)
description: FltPurgeFileNameInformationCache purges from the Filter Manager's name cache all file name information structures that were generated from names provided by the given minifilter driver instance.
old-location: ifsk\fltpurgefilenameinformationcache.htm
tech.root: ifsk
ms.assetid: d3c4d041-0589-46f5-a514-8efb0db642c7
ms.date: 04/16/2018
keywords: ["FltPurgeFileNameInformationCache function"]
ms.keywords: FltApiRef_p_to_z_2b9315b1-c1c1-4739-af0e-0acebae1c59e.xml, FltPurgeFileNameInformationCache, FltPurgeFileNameInformationCache function [Installable File System Drivers], fltkernel/FltPurgeFileNameInformationCache, ifsk.fltpurgefilenameinformationcache
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltPurgeFileNameInformationCache
 - fltkernel/FltPurgeFileNameInformationCache
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltPurgeFileNameInformationCache
---

# FltPurgeFileNameInformationCache function


## -description

<b>FltPurgeFileNameInformationCache</b> purges from the Filter Manager's name cache all file name information structures that were generated from names provided by the given minifilter driver instance.

## -parameters

### -param Instance 

[in]
Opaque instance (PFLT_INSTANCE) pointer for the minifilter driver instance whose names are to be purged. This parameter is required and cannot be <b>NULL</b>.

### -param FileObject 

[in, optional]
Optional pointer to a file object for which all names are to be purged. If this parameter is <b>NULL</b>, all names for the minifilter driver instance specified by the <i>Instance</i> parameter are purged.

## -returns

<b>FltPurgeFileNameInformationCache</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value.

## -remarks

A minifilter driver that provides file names for the Filter Manager's name cache can call <b>FltPurgeFileNameInformationCache</b> to purge the names provided for a given minifilter driver instance. This is most commonly done when a name-providing filter unloads. 

The file name information structures are not freed until all references are released.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_name_control">FLT_NAME_CONTROL</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcheckandgrownamecontrol">FltCheckAndGrowNameControl</a>



<a href="/previous-versions/ff543030(v=vs.85)">FltGetFileNameFormat</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilenameinformation">FltGetFileNameInformation</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilenameinformationunsafe">FltGetFileNameInformationUnsafe</a>



<a href="/previous-versions/ff543040(v=vs.85)">FltGetFileNameQueryMethod</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_generate_file_name">PFLT_GENERATE_FILE_NAME</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_normalize_context_cleanup">PFLT_NORMALIZE_CONTEXT_CLEANUP</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_normalize_name_component">PFLT_NORMALIZE_NAME_COMPONENT</a>