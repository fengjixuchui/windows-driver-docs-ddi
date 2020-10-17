---
UID: NF:fltkernel.FltCreateSectionForDataScan
title: FltCreateSectionForDataScan function (fltkernel.h)
description: The FltCreateSectionForDataScan routine creates a section object for a file. The filter manager can optionally synchronize I/O with the section created.
old-location: ifsk\fltcreatesectionfordatascan.htm
tech.root: ifsk
ms.assetid: D1215495-C737-45B6-BECD-8CB430C71DE8
ms.date: 04/16/2018
keywords: ["FltCreateSectionForDataScan function"]
ms.keywords: FltCreateSectionForDataScan, FltCreateSectionForDataScan routine [Installable File System Drivers], fltkernel/FltCreateSectionForDataScan, ifsk.fltcreatesectionfordatascan
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: The FltCreateSectionForDataScan routine is available starting with  Windows 8.
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
req.dll: 
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltCreateSectionForDataScan
 - fltkernel/FltCreateSectionForDataScan
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltCreateSectionForDataScan
---

# FltCreateSectionForDataScan function


## -description

The <b>FltCreateSectionForDataScan</b> routine creates a section object for a file. The filter manager can optionally synchronize I/O with the section created.

## -parameters

### -param Instance 

[in]
The opaque instance pointer for the minifilter driver instance whose context is to be retrieved.

### -param FileObject 

[in]
The file object for an open file.  The section object will be backed by the specified file. This parameter is required and cannot be <b>NULL</b>.

### -param SectionContext 

[in]
A pointer to a previously allocated section context.

### -param DesiredAccess 

[in]
The type  of access for the section object as one or more of the following <a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> flags. 

<table>
<tr>
<th><i>DesiredAccess</i> flag</th>
<th>Allows caller to </th>
</tr>
<tr>
<td>
SECTION_MAP_READ

</td>
<td>
Read views of the section.

</td>
</tr>
<tr>
<td>
SECTION_MAP_WRITE

</td>
<td>
Write views of the section.

</td>
</tr>
<tr>
<td>
SECTION_QUERY

</td>
<td>
Query the section object for information about the section. Drivers should set this flag.

</td>
</tr>
<tr>
<td>
SECTION_ALL_ACCESS

</td>
<td>
All actions defined by the previous flags as well as that defined by STANDARD_RIGHTS_REQUIRED. (For more information about STANDARD_RIGHTS_REQUIRED, see <a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>.) 

</td>
</tr>
</table>

### -param ObjectAttributes 

[in, optional]
A pointer to an <a href="/windows/win32/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use the <a href="/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a> macro to initialize this structure. Because <b>FltCreateSectionForDataScan</b> inserts this object into the process handle table, the caller must specify the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>.

### -param MaximumSize 

[in, optional]
This parameter is reserved for future use.

### -param SectionPageProtection 

[in]
The protection to place on each page in the section. Specify one of the following values. This parameter is required and cannot be zero. 

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
PAGE_READONLY

</td>
<td>
Enables read-only access to the committed region of pages. An attempt to write to the committed region results in an access violation. If the system differentiates between read-only access and execute access, an attempt to execute code in the committed region results in an access violation.

</td>
</tr>
<tr>
<td>
PAGE_READWRITE

</td>
<td>
Enables both read and write access to the committed region of pages.

</td>
</tr>
</table>

### -param AllocationAttributes 

[in]
Bitmasks of the SEC_<i>XXX</i> flags determine the allocation attributes of the section. Specify one or more of the following values. This parameter is required and cannot be zero. 

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
SEC_COMMIT

</td>
<td>
Allocates physical storage in memory or in the paging file on disk for all pages of a section. This is the default setting. Note that this flag is required and cannot be omitted.

</td>
</tr>
<tr>
<td>
SEC_FILE

</td>
<td>
The file specified by the <i>FileObject</i> parameter is a mapped file.

</td>
</tr>
</table>

### -param Flags 

[in]
This parameter is reserved for future use.

### -param SectionHandle 

[out]
A pointer to a caller-allocated variable that receives an opaque handle to the section handle.

### -param SectionObject 

[out]
A pointer to a caller-allocated variable that receives an opaque pointer to the section object.

### -param SectionFileSize 

[out, optional]
A pointer to a caller-allocated variable that receives the size, in bytes, of the file at the time the section object was created. This parameter is optional and can be <b>NULL</b>.

## -returns

<b>FltCreateSectionForDataScan</b> returns <b>STATUS_SUCCESS</b> or an appropriate <b>NTSTATUS</b> value, such as one of the following.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_END_OF_FILE</b></dt>
</dl>
</td>
<td width="60%">
The size of the file specified by the <i>FileObject</i> parameter is zero.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b> 
STATUS_FILE_LOCK_CONFLICT</b></dt>
</dl>
</td>
<td width="60%">
 
The file specified by the <i>FileObject</i> parameter is locked.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b> 
STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FltCreateSectionForDataScan</b> encountered a pool allocation failure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_FILE_FOR_SECTION</b></dt>
</dl>
</td>
<td width="60%">
The file specified by the <i>FileObject</i> parameter does not support sections.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The minifilter is not registered.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_8</b></dt>
</dl>
</td>
<td width="60%">
The value specified for the <i>SectionPageProtection</i> parameter is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b> 
STATUS_INVALID_PARAMETER_9</b></dt>
</dl>
</td>
<td width="60%">
 
The caller specified an invalid value for the <i>AllocationAttributes</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The volume attached to this instance does not support section contexts.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PRIVILEGE_NOT_HELD</b></dt>
</dl>
</td>
<td width="60%">

The caller did not have the required privileges to create a section object with the access specified in the <i>DesiredAccess</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FILE_IS_A_DIRECTORY</b></dt>
</dl>
</td>
<td width="60%">

The file specified by the <i>FileObject</i> parameter is a directory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_CONTEXT_ALREADY_DEFINED</b></dt>
</dl>
</td>
<td width="60%">
The filter instance specified by <i>Instance</i> already has an open section for the stream. Only one section per stream, and therefore, per instance is supported.

</td>
</tr>
</table>

## -remarks

Prior to calling <b>FltCreateSectionForDataScan</b>, a minifilter must  first register its volume for data scanning by calling <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltregisterfordatascan">FltRegisterForDataScan</a>. As with other filter context elements, <i>SectionContext</i> is first allocated with <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>. 

Certain situations can occur where holding a section open is incompatible with current file I/O. In particular, file I/O that triggers a cache purge can cause cache incoherency if the cache purge is prevented because of an open section.  A minifilter can provide an optional callback routine for notifications of these events. The minifilter driver implements a <a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_section_conflict_notification_callback">PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK</a> to receive these notifications. Conflict notifications are enabled if the <b>SectionNotificationCallback</b> member of <a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_registration">FLT_REGISTRATION</a> is set to this callback routine when the minifilter is registered. When a notification is received, the section can be closed to allow the conflicting I/O operation to continue. 

<div class="alert"><b>Note</b>  A section notification callback may occur before <b>FltCreateSectionForDataScan</b> returns. A minifilter must be able  to receive the callback and handle the case where <i>SectionHandle</i> and <i>SectionObject</i> are not yet valid.</div>
<div> </div>
When the section object created by this routine is no longer necessary, be sure to close the section object's handle (<i>SectionHandle</i>) by calling the <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a> routine and dereference the section object itself (<i>SectionObject</i>) by calling the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a> routine.

For overview  information on creating mapped sections and views of memory, see <a href="/windows-hardware/drivers/kernel/section-objects-and-views">Section Objects and Views</a>. Also, see the documentation for the <b>CreateFileMapping</b> routine in the Microsoft Windows SDK. 

<div class="alert"><b>Important</b>  <p class="note">Minifilters must not explicitly delete a section context passed to <b>FltCreateSectionForDataScan</b>. Do not call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletecontext">FltDeleteContext</a> after a section context is passed to  <b>FltCreateSectionForDataScan</b>. A section context is deallocated and removed from a stream  by calling <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltclosesectionfordatascan">FltCloseSectionForDataScan</a> in this case.

<p class="note">In general, sections should be created as read-only. In particular, if a read-only file is in a transaction  and a minifilter does not create a read-only section, a write to the section is discarded and is not included as part of the transaction.

</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpurgecachesection">CcPurgeCacheSection</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_registration">FLT_REGISTRATION</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltclosesectionfordatascan">FltCloseSectionForDataScan</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltregisterfordatascan">FltRegisterForDataScan</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_section_conflict_notification_callback">PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatesection">ZwCreateSection</a>