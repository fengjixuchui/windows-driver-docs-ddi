---
UID: NF:storport.StorPortInterlockedRemoveHeadList
title: StorPortInterlockedRemoveHeadList function (storport.h)
description: The StorPortInterlockedRemoveHeadList routine removes an entry from the beginning of a doubly linked list of STOR_LIST_ENTRY structures.
old-location: storage\storportinterlockedremoveheadlist.htm
tech.root: storage
ms.assetid: 6B99D78A-B582-4114-9472-D01D39FDD4C9
ms.date: 03/29/2018
keywords: ["StorPortInterlockedRemoveHeadList function"]
ms.keywords: StorPortInterlockedRemoveHeadList, StorPortInterlockedRemoveHeadList routine [Storage Devices], storage.storportinterlockedremoveheadlist, storport/StorPortInterlockedRemoveHeadList
req.header: storport.h
req.include-header: Storport.h
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortInterlockedRemoveHeadList
 - storport/StorPortInterlockedRemoveHeadList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortInterlockedRemoveHeadList
---

# StorPortInterlockedRemoveHeadList function


## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The StorPortInterlockedRemoveHeadList routine removes an entry from the beginning of a doubly linked list of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_stor_list_entry">STOR_LIST_ENTRY</a> structures.

## -parameters

### -param HwDeviceExtension 

[in]
A pointer to the hardware device extension for the host bus adapter (HBA).

### -param ListHead 

[in, out]
Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_stor_list_entry">STOR_LIST_ENTRY</a> structure that represents the head of the list.

### -param Result

<p>Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_stor_list_entry"><b>STOR_LIST_ENTRY</b></a> structure that represents the entry removed from the list. If the list was empty, the routine returns <b>NULL</b>.</p>

### -param Lock 

[in, out]
A pointer to a <b>STOR_KSPIN_LOCK</b> structure that serves as the spin lock used to synchronize access to the list. The storage for the spin lock must be resident and must have been initialized by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitializespinlock">StorPortInitializeSpinLock</a>.

 You must use this spin lock only with the <b>StorPortInterlocked<i>Xxx</i>List</b> routines.

## -returns

<b>StorPortInterlockedRemoveHeadList</b> returns one of the following status codes:

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
The list items were removed successfully or the list is already empty.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
A pointer in <i>ListHead</i> or <i>Result</i> is <b>NULL</b>.

</td>
</tr>
</table>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-initializelisthead">InitializeListHead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-insertheadlist">InsertHeadList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitializespinlock">StorPortInitializeSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinterlockedinserttaillist">StorPortInterlockedInsertTailList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinterlockedremoveheadlist">StorPortInterlockedRemoveHeadList</a>

