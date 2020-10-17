---
UID: NF:ntddk.RtlNumberGenericTableElementsAvl
title: RtlNumberGenericTableElementsAvl function (ntddk.h)
description: The RtlNumberGenericTableElementsAvl routine returns the number of elements in a generic table.
old-location: ifsk\rtlnumbergenerictableelementsavl.htm
tech.root: ifsk
ms.assetid: CC67993A-99B1-41DC-9278-7A475EF87089
ms.date: 04/16/2018
keywords: ["RtlNumberGenericTableElementsAvl function"]
ms.keywords: RtlNumberGenericTableElementsAvl, RtlNumberGenericTableElementsAvl routine [Installable File System Drivers], ifsk.rtlnumbergenerictableelementsavl, ntddk/RtlNumberGenericTableElementsAvl
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlNumberGenericTableElementsAvl
 - ntddk/RtlNumberGenericTableElementsAvl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlNumberGenericTableElementsAvl
---

# RtlNumberGenericTableElementsAvl function


## -description

The <b>RtlNumberGenericTableElementsAvl</b> routine returns the number of elements in a generic table.

## -parameters

### -param Table 

[in]
Pointer to the generic table (<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_avl_table">RTL_AVL_TABLE</a>). The table must have been initialized by calling <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictableavl">RtlInitializeGenericTableAvl</a>.

## -returns

<b>RtlNumberGenericTableElementsAvl</b> returns the number of elements that are currently stored in the table.

## -remarks

By default, the operating system uses splay trees to implement generic tables, but the <b>RtlNumberGenericTableElementsAvl</b> routine only works with Adelson-Velsky/Landis (AVL) trees. To configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

`#define RTL_USE_AVL_TABLES 0`

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <b>RtlNumberGenericTableElementsAvl</b> routine instead of <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlnumbergenerictableelements">RtlNumberGenericTableElements</a>. In the call to <b>RtlNumberGenericTableElementsAvl</b>, the caller must pass a <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_avl_table">RTL_AVL_TABLE</a> table structure rather than <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_generic_table">RTL_GENERIC_TABLE</a>.

Callers of the<i> Rtl..GenericTableAvl</i> routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlNumberGenericTableElementsAvl</b> must be running at IRQL < DISPATCH_LEVEL if the caller-allocated memory for the generic table is pageable.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictableavl">RtlInitializeGenericTableAvl</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlisgenerictableemptyavl">RtlIsGenericTableEmptyAvl</a>