---
UID: NF:ntifs.CcSetFileSizes
title: CcSetFileSizes function (ntifs.h)
description: The CcSetFileSizes routine updates the cache maps and section object for a cached file whose size has changed.
old-location: ifsk\ccsetfilesizes.htm
tech.root: ifsk
ms.assetid: 1fc92167-ceab-4f8e-bd80-a8f1821846ed
ms.date: 04/16/2018
ms.keywords: CcSetFileSizes, CcSetFileSizes routine [Installable File System Drivers], ccref_2d554d89-6378-4a7c-8984-cb54b9e9e01c.xml, ifsk.ccsetfilesizes, ntifs/CcSetFileSizes
ms.topic: function
f1_keywords:
 - "ntifs/CcSetFileSizes"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- CcSetFileSizes
product:
- Windows
targetos: Windows
req.typenames: 
---

# CcSetFileSizes function


## -description


The <b>CcSetFileSizes</b> routine updates the cache maps and section object for a cached file whose size has changed.


## -parameters




### -param FileObject [in]

Pointer to a file object for the cached file.


### -param FileSizes [in]

Pointer to a CC_FILE_SIZES structure containing <b>AllocationSize</b>, <b>FileSize</b> and <b>ValidDataLength</b> for the file. This structure is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _CC_FILE_SIZES {
    LARGE_INTEGER AllocationSize;
    LARGE_INTEGER FileSize;
    LARGE_INTEGER ValidDataLength;
} CC_FILE_SIZES, *PCC_FILE_SIZES;</pre>
</td>
</tr>
</table></span></div>
<table>
<tr>
<th>Member</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>AllocationSize</b>

</td>
<td>
New section object size for the file. 

</td>
</tr>
<tr>
<td>
<b>FileSize</b>

</td>
<td>
New file size for the file.

</td>
</tr>
<tr>
<td>
<b>ValidDataLength</b>

</td>
<td>
New valid data length for the file.

</td>
</tr>
</table>
 


## -returns



None




## -remarks



File systems must call <b>CcSetFileSizes</b> to update the cache manager data structures whenever one of the following changes is made to a cached file:

<ul>
<li>
Its allocation size is increased.

</li>
<li>
Its valid data length is decreased.

</li>
<li>
Its valid data length is increased by a non-cached I/O operation.

</li>
<li>
Its file size is increased or decreased.

</li>
</ul>
If any failure occurs, <b>CcSetFileSizes</b> raises a status exception for that particular failure. For example, if a pool allocation failure occurs, <b>CcSetFileSizes</b> raises a STATUS_INSUFFICIENT_RESOURCES exception. Therefore, to gain control if a failure occurs, the driver should wrap the call to <b>CcSetFileSizes</b> in a <b>try-except</b> or <b>try-finally</b> statement.

To cache a file, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>.

The <b>CcGetFileSizePointer</b> macro returns the size of a file, given a pointer to a file object for the file.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>PLARGE_INTEGER CcGetFileSizePointer(
  [in] PFILE_OBJECT FileObject
);
</pre>
</td>
</tr>
</table></span></div>
Parameters

<i>FileObject [in]</i>

Pointer to a file object for the file whose size is to be returned.

Return value

A pointer to a member of the cache manager structure for this file that specifies the file size in bytes.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>
 

 

