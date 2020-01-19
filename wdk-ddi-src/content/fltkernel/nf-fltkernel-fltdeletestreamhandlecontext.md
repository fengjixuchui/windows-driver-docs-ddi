---
UID: NF:fltkernel.FltDeleteStreamHandleContext
title: FltDeleteStreamHandleContext function (fltkernel.h)
description: FltDeleteStreamHandleContext removes a context that a given minifilter driver instance has set for a given stream handle and marks the context for deletion.
old-location: ifsk\fltdeletestreamhandlecontext.htm
tech.root: ifsk
ms.assetid: aef71769-cad5-4bb4-9068-74664c22dffe
ms.date: 04/16/2018
ms.keywords: FltApiRef_a_to_d_445c2977-ef26-4cc6-9fb3-1873fbb976f2.xml, FltDeleteStreamHandleContext, FltDeleteStreamHandleContext function [Installable File System Drivers], fltkernel/FltDeleteStreamHandleContext, ifsk.fltdeletestreamhandlecontext
ms.topic: function
f1_keywords:
 - "fltkernel/FltDeleteStreamHandleContext"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltDeleteStreamHandleContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltDeleteStreamHandleContext function


## -description


<b>FltDeleteStreamHandleContext</b> removes a context that a given minifilter driver instance has set for a given stream handle and marks the context for deletion. 


## -parameters




### -param Instance [in]

Opaque instance pointer for the minifilter driver instance whose context is to be removed from the list of contexts attached to the stream handle. 


### -param FileObject [in]

Pointer to a file object for the file stream. 


### -param OldContext [out]

Pointer to a caller-allocated variable that receives the address of the deleted context. This parameter is optional and can be <b>NULL</b>. If <i>OldContext</i> is not <b>NULL</b> and does not point to NULL_CONTEXT, the caller is responsible for calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a> to release this context when it is no longer needed. 


## -returns



<b>FltDeleteStreamHandleContext</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>Instance</i> is being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No matching context was found. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The file system does not support per-stream contexts for this file stream. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



Because contexts are reference-counted, it is not usually necessary for a minifilter driver to call a routine such as <b>FltDeleteStreamHandleContext</b> to explicitly delete a context. 

A minifilter driver calls <b>FltDeleteStreamHandleContext</b> to remove a context from a stream handle and mark the context for deletion. The context is usually freed immediately unless there is an outstanding reference on it (for example, because the context is still in use by another thread). 

To allocate a new context, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>. 

To get a stream handle context, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetstreamhandlecontext">FltGetStreamHandleContext</a>. 

To set a stream handle context, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetstreamhandlecontext">FltSetStreamHandleContext</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletecontext">FltDeleteContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetstreamhandlecontext">FltGetStreamHandleContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetstreamhandlecontext">FltSetStreamHandleContext</a>
 

 

