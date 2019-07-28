---
UID: NF:mrxfcb.RxAcquireExclusiveFcbResourceInMRx
title: RxAcquireExclusiveFcbResourceInMRx function (mrxfcb.h)
description: RxAcquireExclusiveFcbResourceInMRx acquires the FCB resource for a network mini-redirector driver in exclusive mode.
old-location: ifsk\rxacquireexclusivefcbresourceinmrx.htm
tech.root: ifsk
ms.assetid: 417c3ffd-5c40-430d-9aec-169203dba685
ms.date: 04/16/2018
ms.keywords: RxAcquireExclusiveFcbResourceInMRx, RxAcquireExclusiveFcbResourceInMRx routine [Installable File System Drivers], ifsk.rxacquireexclusivefcbresourceinmrx, mrxfcb/RxAcquireExclusiveFcbResourceInMRx, rxref_54a3508a-7d99-487a-9363-a13500540230.xml
ms.topic: function
f1_keywords:
 - "mrxfcb/RxAcquireExclusiveFcbResourceInMRx"
req.header: mrxfcb.h
req.include-header: Mrxfcb.h
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
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- mrxfcb.h
api_name:
- RxAcquireExclusiveFcbResourceInMRx
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxAcquireExclusiveFcbResourceInMRx function


## -description


<b>RxAcquireExclusiveFcbResourceInMRx</b> acquires the FCB resource for a network mini-redirector driver in exclusive mode. This routine will wait for the FCB resource to be free if it was previously acquired and does not return control until the exclusive resource has been acquired. 


## -parameters




### -param Fcb

<p>A pointer to the FCB. This parameter is required and cannot be <b>NULL</b>. </p>




## -returns



<b>RxAcquireExclusiveFcbResourceInMRx</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_LOCK_NOT_GRANTED</b></dt>
</dl>
</td>
<td width="60%">
The FCB resource was not acquired.

</td>
</tr>
</table>
 




## -remarks



The synchronization resources of interest to a network mini-redirector driver are primarily associated with the FCB. There is a paging I/O resource and a regular resource. The paging I/O resource is managed internally by RDBSS. The only resource accessible to a network mini-redirector driver is the regular resource which should be accessed using <b>RxAcquireExclusiveFcbResourceInMRx</b>, <b>RxAcquireExclusiveFcbResourceInMRxEx</b>, or <b>RxAcquireSharedFcbResourceInMRx</b>, depending on the acquired mode desired. 

<b>RxAcquireExclusiveFcbResourceInMRx</b> will wait for the FCB resource to be free if it was previously acquired  and does not return control until the exclusive resource has been acquired. This routine acquires the FCB resource even if the RX_CONTEXT associated with this FCB has been canceled.

An FCB resource acquired with <b>RxAcquireExclusiveFcbResourceInMRx </b>should be released by calling <b>RxReleaseFcbResourceInMRx</b> or <b>RxReleaseFcbResourceForThreadInMRx</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mrxfcb/nf-mrxfcb-rxacquiresharedfcbresourceinmrx">RxAcquireSharedFcbResourceInMRx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mrxfcb/nf-mrxfcb-rxacquiresharedfcbresourceinmrxex">RxAcquireSharedFcbResourceInMRxEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mrxfcb/nf-mrxfcb-rxreleasefcbresourceforthreadinmrx">RxReleaseFcbResourceForThreadInMRx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mrxfcb/nf-mrxfcb-rxreleasefcbresourceinmrx">RxReleaseFcbResourceInMRx</a>
 

 

