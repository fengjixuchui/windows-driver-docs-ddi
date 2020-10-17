---
UID: NF:storport.StorPortInterlockedPopEntrySList
title: StorPortInterlockedPopEntrySList function (storport.h)
description: Removes an item from the front of a Storport managed singly linked list. Access to the list is synchronized on a multiprocessor system. Syntax.
old-location: storage\storportinterlockedpopentryslist.htm
tech.root: storage
ms.assetid: 9DA0A057-1472-4B42-9149-A961F7D84B2E
ms.date: 03/29/2018
keywords: ["StorPortInterlockedPopEntrySList function"]
ms.keywords: StorPortInterlockedPopEntrySList, StorPortInterlockedPopEntrySList routine [Storage Devices], storage.storportinterlockedpopentryslist, storport/StorPortInterlockedPopEntrySList
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows 8.
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortInterlockedPopEntrySList
 - storport/StorPortInterlockedPopEntrySList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortInterlockedPopEntrySList
---

# StorPortInterlockedPopEntrySList function


## -description

Removes an item from the front of a Storport managed singly linked list. Access to the list is synchronized on a multiprocessor system.
 
Syntax

## -parameters

### -param HwDeviceExtension 

[in]
A pointer to the hardware device extension for the host bus adapter (HBA).

### -param SListHead 

[in, out]
A pointer to an <b>STOR_SLIST_HEADER</b> structure that represents the head of a singly linked list. This structure is considered opaque and is for use by the Storport driver only.

### -param Result 

[out]
A pointer to a list entry pointer. The value returned is a pointer to  the item removed  from the front of the list. If the list is empty, then <b>NULL</b> is returned in the value pointed to by <i>Result</i>.

## -returns

<b>StorPortInterlockedPopEntrySList</b> returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The list item was successfully removed from  the list or is already empty.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
A pointer in <i>SListHead</i> or <i>Result</i> is <b>NULL</b>.

</td>
</tr>
</table>

## -remarks

The <b>StorPortInterlockedPopEntrySList</b> will also return <b>STATUS_SUCCESS</b> when no entries are in the list. The pointer value referenced by <i>Result</i> must be evaluated for <b>NULL</b> to verify that no entry was returned.

<b>StorPortInterlockedPopEntrySList</b> does  not free the list entry it returns. Any deallocation code for the list must take care to free memory allocated for a list entry at the location obtained prior to any adjustment for boundary alignment. The value pointed to by <i>Result</i> may not be the original buffer location allocated due to an adjustment for <b>MEMORY_ALLOCATION_ALIGNMENT</b>. See remarks for <a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportinterlockedpushentryslist">StorPortInterlockedPushEntrySList</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportinitializeslisthead">StorPortInitializeSListHead</a>



<a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportinterlockedflushslist">StorPortInterlockedFlushSList</a>



<a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportinterlockedpushentryslist">StorPortInterlockedPushEntrySList</a>



<a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportquerydepthslist">StorPortQueryDepthSList</a>