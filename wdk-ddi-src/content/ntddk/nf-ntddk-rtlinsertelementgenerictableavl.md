---
UID: NF:ntddk.RtlInsertElementGenericTableAvl
title: RtlInsertElementGenericTableAvl function (ntddk.h)
description: The RtlInsertElementGenericTableAvl routine adds a new entry to a generic table.
old-location: ifsk\rtlinsertelementgenerictableavl.htm
tech.root: ifsk
ms.assetid: BF7563F8-F1C5-4300-94A2-7D884DA7DFA2
ms.date: 04/16/2018
ms.keywords: RtlInsertElementGenericTableAvl, RtlInsertElementGenericTableAvl routine [Installable File System Drivers], ifsk.rtlinsertelementgenerictableavl, ntddk/RtlInsertElementGenericTableAvl
ms.topic: function
f1_keywords:
 - "ntddk/RtlInsertElementGenericTableAvl"
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
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
req.irql: < DISPATCH_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlInsertElementGenericTableAvl
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlInsertElementGenericTableAvl function


## -description


The <b>RtlInsertElementGenericTableAvl</b> routine adds a new entry to a generic table. 


## -parameters




### -param Table [in]

Pointer to a generic Adelson-Velsky/Landis (AVL) table (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_avl_table">RTL_AVL_TABLE</a>) that was initialized by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictableavl">RtlInitializeGenericTableAvl</a>.


### -param Buffer [in]

A caller-allocated buffer that contains the user data to copy into the new element. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictableavl">RtlInitializeGenericTableAvl</a>. 


### -param BufferSize [in]

Size in bytes of data in <i>Buffer.</i>


### -param NewElement [out, optional]

On output, a value of <b>TRUE</b> means the insertion of the new element in the generic table was successful. A value of <b>FALSE</b> means the insertion failed.


## -returns



<b>RtlInsertElementGenericTableAvl</b> returns a pointer to the user data for the newly inserted entry, or the user data for a matching entry that is already in the generic table. If no matching entry is found, but <b>RtlInsertElementGenericTableAvl</b> cannot insert the new entry (for example, because the <i>AllocateRoutine</i> fails), <b>RtlInsertElementGenericTableAvl</b> returns <b>NULL</b>. 




## -remarks



To insert an entry, <b>RtlInsertElementGenericTableAvl</b> calls the <i>CompareRoutine</i> and <i>AllocateRoutine</i> that were registered when the generic table was initialized by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictableavl">RtlInitializeGenericTableAvl</a>. After inserting the new entry, <b>RtlInsertElementGenericTableAvl</b> rebalances the AVL link tree.

When a new entry is inserted into the table, its data is copied from <i>Buffer</i> into the new entry. Thus the pointer returned by <b>RtlInsertElementGenericTableAvl</b> is never equal to <i>Buffer</i>. 

If the caller's <i>CompareRoutine</i> returns <b>GenericEqual</b>, the data at <i>Buffer</i> is assumed to duplicate the data for an existing entry in the generic table. In this case, <b>RtlInsertElementGenericTableAvl</b> does not add the new entry (and thus does not call the <i>AllocateRoutine</i>), because a generic table cannot have duplicate entries.

If a matching entry already exists in the generic table, <b>RtlInsertElementGenericTableAvl</b> returns a pointer to the existing entry's data and sets <i>NewElement</i> to <b>FALSE</b>. 

If there is no matching entry in the table already,<b>RtlInsertElementGenericTableAvl</b> routine allocates sufficient space for the user data of new entry (<i>BufferSize</i>) plus the links associated with the new entry. Thus the total number of bytes will be at least <i>BufferSize</i> + <b>sizeof</b>(BALANCED_LINKS). Caller should not use the first <b>sizeof</b>(BALANCED_LINKS) bytes of the memory that the <i>AllocateRoutine</i>allocates.

Callers of the <i>Rtl..GenericTableAvl</i> routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. 

By default, the operating system uses splay trees to implement generic tables, but the <b>RtlInsertElementGenericTableAvl</b> routine only works with Adelson-Velsky/Landis (AVL) trees. To configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

#define RTL_USE_AVL_TABLES 0

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <b>RtlInsertElementGenericTableAvl</b> routine instead of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertelementgenerictable">RtlInsertElementGenericTable</a>. In the call to <b>RtlInsertElementGenericTableAvl</b>, the caller must pass a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_avl_table">RTL_AVL_TABLE</a> table structure rather than <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_generic_table">RTL_GENERIC_TABLE</a>.

Callers of <b>RtlInsertElementGenericTableAvl</b> must be running at IRQL < DISPATCH_LEVEL if either of the following conditions holds:

<ul>
<li>
The caller-allocated memory at <i>Table</i> or at <i>Buffer</i> is pageable.

</li>
<li>
The caller-supplied <i>CompareRoutine</i> or <i>AllocateRoutine</i> contains pageable code. 

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtldeleteelementgenerictableavl">RtlDeleteElementGenericTableAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictableavl">RtlInitializeGenericTableAvl</a>
 

 

