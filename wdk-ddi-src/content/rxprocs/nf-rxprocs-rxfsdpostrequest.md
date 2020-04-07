---
UID: NF:rxprocs.RxFsdPostRequest
title: RxFsdPostRequest function (rxprocs.h)
description: RxFsdPostRequest queues the I/O request packet (IRP) specified by an RX_CONTEXT structure to the worker queue for processing by the file system process (FSP).
old-location: ifsk\rxfsdpostrequest.htm
tech.root: ifsk
ms.assetid: 0b1bc248-6b8e-498c-936d-64f6ff9fa183
ms.date: 04/16/2018
keywords: ["RxFsdPostRequest function"]
ms.keywords: RxFsdPostRequest, RxFsdPostRequest function [Installable File System Drivers], ifsk.rxfsdpostrequest, rxprocs/RxFsdPostRequest, rxref_ceb83e58-1e5a-49d0-b281-50cd5067e09f.xml
f1_keywords:
 - "rxprocs/RxFsdPostRequest"
req.header: rxprocs.h
req.include-header: Rxprocs.h, Rxcontx.h
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- rxprocs.h
api_name:
- RxFsdPostRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxFsdPostRequest function


## -description


<b>RxFsdPostRequest</b> queues the I/O request packet (IRP) specified by an RX_CONTEXT structure to the worker queue for processing by the file system process (FSP). 


## -parameters




### -param RxContext [in]

A pointer to the RX_CONTEXT containing the IRP to be queued to a worker thread.


## -returns



<b>RxFsdPostRequest</b> returns the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
An asynchornous request was made and has been queued to a worker thread for later processing. The status of the request is pending.

</td>
</tr>
</table>
 




## -remarks



<b>RxFsdPostRequest</b> is normally called by RDBSS to process an asynchronous I/O request packet (IRP). These IRPs are normally received by RDBSS in response to a user-mode application requesting operations on a file. It is also possible for another kernel driver to issue such an IRP. 

If the <b>Flags</b> member of the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter does not have the RX_CONTEXT_FLAG_NO_PREPOSTING_NEEDED bit set, then <b>RxFsdPostRequest</b> will try to lock down any user address space that is required for certain types of requests. The requests that result in this behavior are based on the <b>MajorFunction</b> member of RX_CONTEXT structure pointed to by <i>RxContext</i> and include the following:

<ul>
<li>
IRP_MJ_DIRECTORY CONTROL when <b>RxContext->MinorFunction</b><i> is </i>IRP_MN_QUERY_DIRECTORY.

</li>
<li>
IRP_MJ_QUERY_EA

</li>
<li>
IRP_MJ_READ

</li>
<li>
IRP_MJ_SET_EA

</li>
<li>
IRP_MJ_WRITE

</li>
</ul>
The <b>MajorFunction</b> member of <i>RxContext</i> will determine which work queue this request will be posted to. An IRP_MJ_DEVICE_CONTROL request where the <b>Parameters.DeviceIoControl.IoControlCode</b> member is IOCTL_REDIR_QUERY_PATH will be posted to the delayed work queue. In the case, the <b>Flags</b> member of the <i>RxContext</i> parameter will have the RX_CONTEXT_FLAG_FSP_DELAYED_OVERFLOW_QUEUE bit set. All other requests are posted to the critical work queue and the Flags member of the <i>RxContext</i> parameter will have the RX_CONTEXT_FLAG_FSP_CRITICAL_OVERFLOW_QUEUE bit set. 

If the <b>FileObject</b> member of the IRP is not <b>NULL</b> and the request can be posted immediately for processing (the threshold for the device queue is empty), then this will occur. Otherwise, the request will be posted to an overflow queue on the volume.

All calls to <b>RxFsdPostRequest</b> are queued to a worker thread to call the <b>RxFsdDispatch</b> routine passing in the <i>RxContext</i> parameter. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nf-mrx-rxfsddispatch">RxFsdDispatch</a>
 

 

