---
UID: NF:ntifs.FsRtlAllocatePoolWithTag
title: FsRtlAllocatePoolWithTag macro (ntifs.h)
description: The FsRtlAllocatePoolWithTag routine allocates pool memory.
old-location: ifsk\fsrtlallocatepoolwithtag.htm
tech.root: ifsk
ms.assetid: a9ea59d1-1d51-4332-b497-7d2b7f39e686
ms.date: 04/16/2018
keywords: ["FsRtlAllocatePoolWithTag macro"]
ms.keywords: FsRtlAllocatePoolWithTag, FsRtlAllocatePoolWithTag routine [Installable File System Drivers], fsrtlref_1137174c-fe54-4575-98a6-64a569f91b96.xml, ifsk.fsrtlallocatepoolwithtag, ntifs/FsRtlAllocatePoolWithTag
f1_keywords:
 - "ntifs/FsRtlAllocatePoolWithTag"
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
req.irql: <= DISPATCH_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlAllocatePoolWithTag
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlAllocatePoolWithTag macro


## -description


The <b>FsRtlAllocatePoolWithTag</b> routine allocates pool memory. 


## -parameters




### -param PoolType [in]

Type of pool to allocate. One of the following:


<ul>
<li><b>NonPagedPool</b></li>
<li><b>PagedPool</b></li>
<li><b>NonPagedPoolCacheAligned</b></li>
<li><b>PagedPoolCacheAligned</b></li>
</ul>


<div class="alert"><b>Note</b>    The <b>NonPagedPoolMustSucceed</b> and <b>NonPagedPoolCacheAlignedMustS</b> pool types are obsolete and should no longer be used. </div>
<div> </div>

### -param NumberOfBytes [in]

Number of bytes to allocate. This parameter is required and cannot be zero. 


### -param Tag [in]

Specifies the pool tag for the allocated memory. Drivers normally specify the pool tag as a string of one to four 7-bit ASCII characters, delimited by single quotation marks (for example, 'abcd'). This parameter is required and cannot be zero. 


## -remarks



If a pool allocation failure occurs, <b>FsRtlAllocatePoolWithTag</b> raises a STATUS_INSUFFICIENT_RESOURCES exception. To gain control if this pool allocation failure occurs, the driver should wrap the call to <b>FsRtlAllocatePoolWithTag</b> in a <b>try-except</b> or <b>try-finally</b> statement.

The system associates the pool tag specified by the <i>Tag</i> parameter with the allocated buffer. Programming tools, such as the Windows Debugger (WinDbg), can display the pool tag associated with each allocated buffer. The value of the pool tag is normally displayed in reversed order. For example, if a caller passes 'Fred' as the value of the <i>Tag</i> parameter, this value would appear as 'derF' if pool is dumped or when tracking pool usage in the debugger. 

For more information about memory management, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/managing-memory-for-drivers">Memory Management</a>. 

Callers of <b>FsRtlAllocatePoolWithTag</b> must be running at IRQL <= DISPATCH_LEVEL. A caller at DISPATCH_LEVEL must specify a <b>NonPaged</b><i>XxxPoolType</i>. Otherwise, the caller must be running at IRQL <= APC_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a>
 

 

