---
UID: NF:ntddk.RtlEnumerateGenericTable
title: RtlEnumerateGenericTable function (ntddk.h)
description: The RtlEnumerateGenericTable routine is used to enumerate the elements in a generic table.
old-location: ifsk\rtlenumerategenerictable.htm
tech.root: ifsk
ms.assetid: 53a5348c-71d1-4d58-82bf-1f8bf8daff90
ms.date: 04/16/2018
keywords: ["RtlEnumerateGenericTable function"]
ms.keywords: RtlEnumerateGenericTable, RtlEnumerateGenericTable routine [Installable File System Drivers], ifsk.rtlenumerategenerictable, ntddk/RtlEnumerateGenericTable, rtlref_5fb7c196-aee1-4dcc-a39c-587472a2fbe9.xml
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
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
req.irql: < DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlEnumerateGenericTable
 - ntddk/RtlEnumerateGenericTable
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlEnumerateGenericTable
---

# RtlEnumerateGenericTable function


## -description

The <b>RtlEnumerateGenericTable</b> routine is used to enumerate the elements in a generic table.

## -parameters

### -param Table 

[in]
A pointer to the generic table (<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_generic_table">RTL_GENERIC_TABLE</a>). The table must have been initialized by calling <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictable">RtlInitializeGenericTable</a>.

### -param Restart 

[in]
Set to <b>TRUE</b> if the enumeration is to start at the first element in the table. Set to <b>FALSE</b> if resuming the enumeration from a previous call.

To enumerate all elements in the table, use <b>RtlEnumerateGenericTable</b> as follows:


```
for (p = RtlEnumerateGenericTable ( Table, TRUE );
     p != NULL;
     p = RtlEnumerateGenericTable ( Table, FALSE )) {
        // Process the element pointed to by p
}
```


## -returns

<b>RtlEnumerateGenericTable</b> returns a pointer to the next element, if one exists. If there are no more elements in the table, <b>RtlEnumerateGenericTable</b> returns <b>NULL</b>.

## -remarks

<b>RtlEnumerateGenericTable</b> flattens the generic table by converting it from a splay tree into a sorted linked list. To enumerate the table without flattening it, use <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictablewithoutsplaying">RtlEnumerateGenericTableWithoutSplaying</a>. 

Callers of the <i>Rtl..GenericTable</i> routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. 

By default, the operating system uses splay trees to implement generic tables. Under some circumstances, operations on a splay tree will make the tree deep and narrow and might even turn it into a straight line. Very deep trees degrade the performance of searches. You can ensure a more balanced, shallower tree implementation of generic tables by using Adelson-Velsky/Landis (AVL) trees. If you want to configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

`#define RTL_USE_AVL_TABLES 0`

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictableavl">RtlEnumerateGenericTableAvl</a> routine instead of <b>RtlEnumerateGenericTable</b>. In the call to <b>RtlEnumerateGenericTableAvl</b>, the caller must pass a <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_avl_table">RTL_AVL_TABLE</a> table structure rather than <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_generic_table">RTL_GENERIC_TABLE</a>.

Callers of <b>RtlEnumerateGenericTable</b> must be running at IRQL < DISPATCH_LEVEL if the caller-allocated memory for the generic table is pageable.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializefastmutex">ExInitializeFastMutex</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictablewithoutsplaying">RtlEnumerateGenericTableWithoutSplaying</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictable">RtlInitializeGenericTable</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlisgenerictableempty">RtlIsGenericTableEmpty</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlnumbergenerictableelements">RtlNumberGenericTableElements</a>