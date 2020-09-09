---
UID: NF:fltkernel.FltQueueDeferredIoWorkItem
title: FltQueueDeferredIoWorkItem function (fltkernel.h)
description: The FltQueueDeferredIoWorkItem routine posts an IRP-based I/O operation to a work queue.
old-location: ifsk\fltqueuedeferredioworkitem.htm
tech.root: ifsk
ms.assetid: c6a51b9b-544e-4595-842a-76c667928350
ms.date: 04/16/2018
keywords: ["FltQueueDeferredIoWorkItem function"]
ms.keywords: FltApiRef_p_to_z_df42429d-485c-4c28-a9e7-b334d7ad52d7.xml, FltQueueDeferredIoWorkItem, FltQueueDeferredIoWorkItem routine [Installable File System Drivers], fltkernel/FltQueueDeferredIoWorkItem, ifsk.fltqueuedeferredioworkitem
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available in Microsoft Windows 2000 and later versions of all Windows operating systems.
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltQueueDeferredIoWorkItem
 - fltkernel/FltQueueDeferredIoWorkItem
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltQueueDeferredIoWorkItem
---

# FltQueueDeferredIoWorkItem function


## -description

The <b>FltQueueDeferredIoWorkItem</b> routine posts an IRP-based I/O operation to a work queue.

## -parameters

### -param FltWorkItem 

[in]
A pointer to the work item to add to the work queue. The work item must have been allocated by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatedeferredioworkitem">FltAllocateDeferredIoWorkItem</a>.

### -param Data 

[in]
A pointer to the callback data (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) structure for the I/O operation. The operation must be an IRP-based I/O operation. To determine whether a given callback data structure represents an IRP-based I/O operation, use the <a href="https://docs.microsoft.com/previous-versions/ff544654(v=vs.85)">FLT_IS_IRP_OPERATION</a> macro.

### -param WorkerRoutine 

[in]
A pointer to a caller-supplied worker routine. This routine is declared as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
(*PFLT_DEFERRED_IO_WORKITEM_ROUTINE) (
      _in PFLT_DEFERRED_IO_WORKITEM  FltWorkItem,
      __in PFLT_CALLBACK_DATA  CallbackData,
      __in_opt PVOID  Context
      );</pre>
</td>
</tr>
</table></span></div>




#### FltWorkItem

An opaque pointer to a deferred work item structure. 



#### CallbackData

A pointer to the callback data structure for the I/O operation. 



#### Context

An optional context information pointer that was passed as the <i>Context</i> parameter of <b>FltQueueDeferredIoWorkItem</b>.

### -param QueueType 

[in]
This parameter specifies the queue into which the work item that <i>FltWorkItem</i> points to is to be inserted. <i>QueueType</i> can be either of the following. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>CriticalWorkQueue</b>

</td>
<td>
Insert the work item into the queue from which a system thread with a real-time priority attribute processes the work item. 

</td>
</tr>
<tr>
<td>
<b>DelayedWorkQueue</b>

</td>
<td>
Insert the work item into the queue from which a system thread with a variable priority attribute processes the work item. 

</td>
</tr>
</table>
 

The <i>QueueType</i> value <b>HyperCriticalWorkQueue</b> is reserved for system use.

### -param Context 

[in]
A pointer to caller-defined context information to be passed as the <i>Context</i> parameter of the callback routine specified in the <i>WorkerRoutine</i> parameter.

## -returns

The <b>FltQueueDeferredIoWorkItem</b> routine returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

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
The target instance for the I/O operation (<i>Data->Iopb->TargetInstance</i>) is being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_NOT_SAFE_TO_POST_OPERATION</b></dt>
</dl>
</td>
<td width="60%">
The I/O operation cannot be posted safely to a worker thread. Possible reasons include the following: 

<ul>
<li>
<b>FltQueueDeferredIoWorkItem</b> cannot post an I/O operation to a worker thread if the <b>TopLevelIrp</b> field of the current thread is not <b>NULL</b>, because the resulting file system recursion could cause deadlocks or stack overflows. (For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iogettoplevelirp">IoGetTopLevelIrp</a>.) 

</li>
<li>
<b>FltQueueDeferredIoWorkItem</b> cannot post a paging I/O operation to a worker thread. 

</li>
</ul>
STATUS_FLT_NOT_SAFE_TO_POST_OPERATION is an error code. 

</td>
</tr>
</table>

## -remarks

The <b>FltQueueDeferredIoWorkItem</b> routine posts an I/O operation to a system work queue. The specified <i>WorkerRoutine</i> callback routine is called in the context of a system thread, at IRQL PASSIVE_LEVEL. 

The operation must be an IRP-based I/O operation. To determine whether a given callback data structure represents an IRP-based I/O operation, use the <a href="https://docs.microsoft.com/previous-versions/ff544654(v=vs.85)">FLT_IS_IRP_OPERATION</a> macro. 

A minifilter driver can use <b>FltQueueDeferredIoWorkItem</b> in a preoperation callback (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>) routine as follows: 

<ol>
<li>
The preoperation callback calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatedeferredioworkitem">FltAllocateDeferredIoWorkItem</a> to allocate the work item. 

</li>
<li>
The preoperation callback calls <b>FltQueueDeferredIoWorkItem</b> to post the operation to the work queue. 

</li>
<li>
The preoperation callback returns FLT_PREOP_PENDING. 

</li>
<li>
After processing the I/O operation, the work routine calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcompletependedpreoperation">FltCompletePendedPreOperation</a> to return the I/O operation to the Filter Manager. 

</li>
<li>
The work routine calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreedeferredioworkitem">FltFreeDeferredIoWorkItem</a> to free the work item. 

</li>
</ol>
A minifilter driver can use <b>FltQueueDeferredIoWorkItem</b> in a post-operation callback (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_post_operation_callback">PFLT_POST_OPERATION_CALLBACK</a>) routine as follows: 

<ol>
<li>
The post-operation callback calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatedeferredioworkitem">FltAllocateDeferredIoWorkItem</a> to allocate the work item. 

</li>
<li>
The post-operation callback calls <b>FltQueueDeferredIoWorkItem</b> to post the operation to the work queue. 

</li>
<li>
The post-operation callback returns FLT_POSTOP_MORE_PROCESSING_REQUIRED. 

</li>
<li>
After processing the I/O operation, the work routine calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcompletependedpostoperation">FltCompletePendedPostOperation</a> to return the I/O operation to the Filter Manager. 

</li>
</ol>
The work routine calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreedeferredioworkitem">FltFreeDeferredIoWorkItem</a> to free the work item. 

<div class="alert"><b>Caution</b>  
     To avoid deadlocks, a minifilter must not post an I/O operation to a system work queue in the post-operation callback for any I/O operations that a driver can complete  directly in the storage stack, such as the following:<ul>
<li>
IRP_MJ_READ

</li>
<li>
IRP_MJ_WRITE

</li>
<li>
IRP_MJ_FLUSH_BUFFERS

</li>
</ul>
</div>
<div> </div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/previous-versions/ff544654(v=vs.85)">FLT_IS_IRP_OPERATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatedeferredioworkitem">FltAllocateDeferredIoWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcompletependedpostoperation">FltCompletePendedPostOperation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcompletependedpreoperation">FltCompletePendedPreOperation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreedeferredioworkitem">FltFreeDeferredIoWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iogettoplevelirp">IoGetTopLevelIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_post_operation_callback">PFLT_POST_OPERATION_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>

