---
UID: NF:fltkernel.FltSetFileContext
title: FltSetFileContext function (fltkernel.h)
description: The FltSetFileContext routine sets a context for a file.
old-location: ifsk\fltsetfilecontext.htm
tech.root: ifsk
ms.assetid: d56cb216-a757-4ab8-ac7f-04dc22997835
ms.date: 04/16/2018
keywords: ["FltSetFileContext function"]
ms.keywords: FltApiRef_p_to_z_ef77cece-4fd9-4453-9594-b027037d3ca9.xml, FltSetFileContext, FltSetFileContext routine [Installable File System Drivers], fltkernel/FltSetFileContext, ifsk.fltsetfilecontext
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available and supported starting with Windows Vista. For more information, see the Remarks section.
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
req.lib: Fltmgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltSetFileContext
 - fltkernel/FltSetFileContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltSetFileContext
---

# FltSetFileContext function


## -description

The <b>FltSetFileContext</b> routine sets a context for a file.

## -parameters

### -param Instance 

[in]
An opaque pointer to a minifilter driver instance for the caller. This parameter is required and cannot be <b>NULL</b>.

### -param FileObject 

[in]
A file object pointer for the file. This parameter is required and cannot be <b>NULL</b>.

### -param Operation 

[in]
A flag that specifies the type of operation for <b>FltSetFileContext </b>to perform. This parameter must be one of the following flags:  





#### FLT_SET_CONTEXT_REPLACE_IF_EXISTS

If a context is already set for the instance that the <i>Instance </i>parameter points to, <b>FltSetFileContext</b> will replace that context with the context specified in <i>NewContext</i>. Otherwise, the routine will insert the context specified in <i>NewContext</i> into the list of contexts for the file. 



#### FLT_SET_CONTEXT_KEEP_IF_EXISTS

If a context is already set for the instance that the <i>Instance</i> parameter points to, <b>FltSetFileContext</b> will return STATUS_FLT_CONTEXT_ALREADY_DEFINED. Otherwise, the routine will insert the context specified in <i>NewContext</i> into the list of contexts for the file.

### -param NewContext 

[in]
A pointer to the new context to be set for the file. This parameter is required and cannot be <b>NULL</b>.

### -param OldContext 

[out]
A pointer to a caller-allocated variable that receives the address of the existing file context for the instance pointed to by the <i>Instance </i>parameter. This parameter is optional and can be <b>NULL</b>. For more information about this parameter, see the following Remarks section.

## -returns

The <b>FltSetFileContext</b> routine returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_CONTEXT_ALREADY_DEFINED</b></dt>
</dl>
</td>
<td width="60%">
If FLT_SET_CONTEXT_KEEP_IF_EXISTS was specified for the <i>Operation</i> parameter, this error code indicates that a context is already attached to the file. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_CONTEXT_ALREADY_LINKED</b></dt>
</dl>
</td>
<td width="60%">
The context pointed to by the <i>NewContext</i> parameter is already linked to an object.  In other words, this error code indicates that <i>NewContext</i> is already in use due to a successful prior call of a <b>FltSet</b><i>Xxx</i><b>Context</b> routine. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The instance specified in the <i>Instance</i> parameter is being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
This error code indicates one of the following problems:

<ul>
<li>
The <i>NewContext</i> parameter does not point to a valid file context. 

</li>
<li>
An invalid value was specified for the <i>Operation</i> parameter. 

</li>
</ul>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
File contexts are not supported for this file. This is an error code. 

</td>
</tr>
</table>

## -remarks

The <b>FltSetFileContext</b> routine is available on Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP2, Windows Server 2003 SP1, and later operating systems. This routine is available and supported starting with Windows Vista (file contexts are only supported starting with Windows Vista). If <b>FltSetFileContext</b> is called on an operating system where this routine is available but file contexts are not supported, it returns STATUS_NOT_SUPPORTED.  This routine is not available on Windows 2000 SP4 and earlier operating systems.

A minifilter driver calls <b>FltSetFileContext</b> to set or replace its own file context on a file. A minifilter driver can attach one context per minifilter driver instance to the file. 

A successful call to <b>FltSetFileContext</b> increments the reference count on <i>NewContext</i>. If <b>FltSetFileContext</b> fails, the reference count remains unchanged. In either case, the filter calling <b>FltSetFileContext</b> must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a> to decrement the <i>NewContext</i> object. If <b>FltSetFileContext</b> fails and if the <i>OldContext</i> parameter is not <b>NULL</b> and does not point to NULL_CONTEXT then <i>OldContext</i> is a referenced pointer to the context currently associated with the transaction. The filter calling <b>FltSetFileContext</b> must call <b>FltReleaseContext</b> for <i>OldContext</i> as well.

Note that the <i>OldContext</i> pointer returned by <b>FltSetFileContext</b> must also be released by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a> when it is no longer needed. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/setting-contexts">Setting Contexts</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/releasing-contexts">Releasing Contexts</a>.

Be aware that <b>FltSetFileContext</b> cannot be called on an unopened <i>FileObject</i>. Hence <b>FltSetFileContext</b> cannot be called from a pre-create callback for a stream because the stream has not been opened at that point. A minifilter driver can, however, allocate and set up the stream file context in the pre-create callback, pass it to the post-create callback using the completion context parameter and set the stream file context on the file corresponding to that stream in the post-create callback.

To get a file context, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilecontext">FltGetFileContext</a>. 

To allocate a new context, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>. 

To delete a file context, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletefilecontext">FltDeleteFileContext</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletecontext">FltDeleteContext</a>. 

To determine whether file contexts are supported for a given file, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsupportsfilecontexts">FltSupportsFileContexts</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsupportsfilecontextsex">FltSupportsFileContextsEx</a>. 

For more information about context reference counting, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/referencing-contexts">Referencing Contexts</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_context_registration">FLT_CONTEXT_REGISTRATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletecontext">FltDeleteContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletefilecontext">FltDeleteFileContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilecontext">FltGetFileContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsupportsfilecontexts">FltSupportsFileContexts</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsupportsfilecontextsex">FltSupportsFileContextsEx</a>

