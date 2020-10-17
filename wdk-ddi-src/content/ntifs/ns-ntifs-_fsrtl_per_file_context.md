---
UID: NS:ntifs._FSRTL_PER_FILE_CONTEXT
title: _FSRTL_PER_FILE_CONTEXT (ntifs.h)
description: A legacy file system filter driver can use a FSRTL_PER_FILE_CONTEXT structure to associate driver-specific context information to an open file.
old-location: ifsk\fsrtl_per_file_context.htm
tech.root: ifsk
ms.assetid: d20668f0-b076-4edd-bf21-98841cbbdc74
ms.date: 04/16/2018
keywords: ["FSRTL_PER_FILE_CONTEXT structure"]
ms.keywords: "*PFSRTL_PER_FILE_CONTEXT, FSRTL_PER_FILE_CONTEXT, FSRTL_PER_FILE_CONTEXT structure [Installable File System Drivers], PFSRTL_PER_FILE_CONTEXT, PFSRTL_PER_FILE_CONTEXT structure pointer [Installable File System Drivers], _FSRTL_PER_FILE_CONTEXT, contextstructures_329894da-4955-4f46-8fab-92e32f10ed0d.xml, ifsk.fsrtl_per_file_context, ntifs/FSRTL_PER_FILE_CONTEXT, ntifs/PFSRTL_PER_FILE_CONTEXT"
req.header: ntifs.h
req.include-header: Fltkernel.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting withWindows Vista.
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
req.typenames: FSRTL_PER_FILE_CONTEXT, *PFSRTL_PER_FILE_CONTEXT
f1_keywords:
 - _FSRTL_PER_FILE_CONTEXT
 - ntifs/_FSRTL_PER_FILE_CONTEXT
 - PFSRTL_PER_FILE_CONTEXT
 - ntifs/PFSRTL_PER_FILE_CONTEXT
 - FSRTL_PER_FILE_CONTEXT
 - ntifs/FSRTL_PER_FILE_CONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FSRTL_PER_FILE_CONTEXT
---

# _FSRTL_PER_FILE_CONTEXT structure


## -description

A legacy file system filter driver can use a <b>FSRTL_PER_FILE_CONTEXT</b> structure to associate driver-specific context information to an open file.

## -struct-fields

### -field Links

A link for this structure in the list of all per-file context structures that are associated with the same file. <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlinsertperfilecontext">FsRtlInsertPerFileContext</a> inserts this member into the list of all per-file context structures for a file.

### -field OwnerId

A pointer to a filter-driver-allocated buffer that uniquely identifies the owner of the per-file context structure. The format of this variable is filter-driver-specific.  Filter drivers must set this member to a non-<b>NULL</b> value.

### -field InstanceId

A pointer to a filter-driver-allocated buffer that can be used to distinguish among the per-file context structures that are created by the same filter driver. The format of this variable is filter-driver-specific. Filter drivers can set this member to <b>NULL</b>.

### -field FreeCallback

A pointer to a <a href="/windows-hardware/drivers/ifs/pfree-function">callback routine</a> that frees the per-file context structure. Filter drivers must set this member to a non-<b>NULL</b> value.

## -remarks

In order to associate context information with a file, a legacy filter driver first allocates a <b>FSRTL_PER_FILE_CONTEXT</b> structure and initializes it using <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlinsertperfilecontext">FsRtlInsertPerFileContext</a>. The driver then uses <b>FsRtlInsertPerFileContext</b> to associate that <b>FSRTL_PER_FILE_CONTEXT</b> object with the file. When the system tears down the file context object for a file, it calls <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlteardownperfilecontexts">FsRtlTeardownPerFileContexts</a> which calls the <i>FreeCallback</i> routine that is specified in the <b>FSRTL_PER_FILE_CONTEXT</b> object. That callback must free the driver-specific context object.

Filter writers should choose an <b>OwnerID</b> value that is both meaningful and convenient, such as the address of a driver object or device object. 

Filter writers should choose an <b>InstanceID</b> value that is both meaningful and convenient, such as the address of the file context object for the file. Use the <a href="/previous-versions/ff546051(v=vs.85)">FsRtlGetPerFileContextPointer</a> macro to retrieve that address from a file object.

The <b>FSRTL_PER_FILE_CONTEXT</b> structure can be used as-is, or embedded in a driver-defined, per-file context structure.

The <b>FSRTL_PER_FILE_CONTEXT</b> structure can be allocated from paged or nonpaged pool. 

The <b>FsRtlInitPerFileContext</b> macro initializes a <b>FSRTL_PER_FILE_CONTEXT</b> structure.

Parameters

<i>FileContext</i>

<b>FSRTL_PER_FILE_CONTEXT</b>

The FSRTL_PER_FILE_CONTEXT object to be initialized.

<i>OwnerId</i>

<b>PVOID</b>

A pointer to a filter driver-allocated variable that uniquely identifies the owner of the per-file context structure. The format is filter driver-specific. This parameter must have a non-<b>NULL</b> value.

<i>InstanceId</i>

<b>PVOID</b>

A pointer to a filter driver-allocated variable that uniquely identifies the owner of the per-file context structure. The format is filter driver-specific. This parameter must have a non-<b>NULL</b> value.

<i>FreeCallback</i>

<b>PFREE_FUNCTION</b>

A pointer to a <a href="/windows-hardware/drivers/ifs/pfree-function">callback routine</a> that frees the per-file context structure. 

Return value

<b>VOID</b>

None.

This macro must be used before calling <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlinsertperfilecontext">FsRtlInsertPerFileContext</a>.

Filter writers should choose an <i>OwnerID</i> value that is both meaningful and convenient, such as the address of a driver object or device object. 

Filter writers should use an <i>InstanceID</i> value that is both meaningful and convenient, such as the address of the file context object for the file. Use the <b>FsRtlGetPerFileContextPointer</b> macro to retrieve that address from a file object.

For more information about how to use and create context objects, see <a href="/windows-hardware/drivers/ifs/tracking-per-file-context-in-a-legacy-file-system-filter-driver">Tracking Per-File Context in a Legacy File System Filter Driver</a>.

## -see-also

<a href="/previous-versions/ff546051(v=vs.85)">FsRtlGetPerFileContextPointer</a>



<a href="/previous-versions/ff546161(v=vs.85)">FsRtlInitPerFileContext</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlinsertperfilecontext">FsRtlInsertPerFileContext</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlteardownperfilecontexts">FsRtlTeardownPerFileContexts</a>



<a href="/windows-hardware/drivers/ifs/pfree-function">PFREE_FUNCTION</a>



<a href="/windows-hardware/drivers/ifs/tracking-per-file-context-in-a-legacy-file-system-filter-driver">Tracking Per-File Context in a Legacy File System Filter Driver</a>