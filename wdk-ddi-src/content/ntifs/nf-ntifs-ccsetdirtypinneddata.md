---
UID: NF:ntifs.CcSetDirtyPinnedData
title: CcSetDirtyPinnedData function (ntifs.h)
description: The CcSetDirtyPinnedData routine marks as dirty the buffer control block (BCB) for a pinned buffer whose contents have been modified.
old-location: ifsk\ccsetdirtypinneddata.htm
tech.root: ifsk
ms.assetid: f621a54f-ed40-4ec7-8678-7c72fcd9e704
ms.date: 04/16/2018
keywords: ["CcSetDirtyPinnedData function"]
ms.keywords: CcSetDirtyPinnedData, CcSetDirtyPinnedData routine [Installable File System Drivers], ccref_2cd7571b-289f-4510-a5de-f4e38eb049a2.xml, ifsk.ccsetdirtypinneddata, ntifs/CcSetDirtyPinnedData
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - CcSetDirtyPinnedData
 - ntifs/CcSetDirtyPinnedData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcSetDirtyPinnedData
---

# CcSetDirtyPinnedData function


## -description

The <b>CcSetDirtyPinnedData</b> routine marks as dirty the buffer control block (BCB) for a pinned buffer whose contents have been modified.

## -parameters

### -param BcbVoid 

[in]
Pointer to the BCB structure to be marked as dirty.

### -param Lsn 

[in, optional]
Logical sequence number (LSN) to be associated with this buffer.

## -remarks

<b>CcSetDirtyPinnedData</b> marks the BCB as dirty, so that the contents of the pinned buffer will be lazy-written to disk. Even if the flush operation is to be performed by some means other than the lazy writer, <b>CcSetDirtyPinnedData</b> should be called whenever the contents of a pinned buffer are modified. This is especially important if the buffer was pinned only for read access (by <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpinread">CcPinRead</a> or <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpinmappeddata">CcPinMappedData</a>). Although buffers that are pinned only for read access can be modified, their contents are not automatically flushed to disk unless the buffers have been marked as dirty by calling <b>CcSetDirtyPinnedData</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccmapdata">CcMapData</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpinmappeddata">CcPinMappedData</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpinread">CcPinRead</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpreparepinwrite">CcPreparePinWrite</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccunpindata">CcUnpinData</a>