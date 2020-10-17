---
UID: NF:wdm.ExConvertExclusiveToSharedLite
title: ExConvertExclusiveToSharedLite function (wdm.h)
description: The ExConvertExclusiveToSharedLite routine converts a given resource from acquired for exclusive access to acquired for shared access.
old-location: kernel\exconvertexclusivetosharedlite.htm
tech.root: kernel
ms.assetid: 140de330-7e6d-4f23-96cb-ea1228c8036c
ms.date: 03/28/2018
keywords: ["ExConvertExclusiveToSharedLite function"]
ms.keywords: ExConvertExclusiveToSharedLite, ExConvertExclusiveToSharedLite routine [Kernel-Mode Driver Architecture], k102_3c58f8e7-3da6-413d-9662-89a29928a6c1.xml, kernel.exconvertexclusivetosharedlite, wdm/ExConvertExclusiveToSharedLite
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExApcLte3, HwStorPortProhibitedDDIs
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
f1_keywords:
 - ExConvertExclusiveToSharedLite
 - wdm/ExConvertExclusiveToSharedLite
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExConvertExclusiveToSharedLite
---

# ExConvertExclusiveToSharedLite function


## -description

The <b>ExConvertExclusiveToSharedLite</b> routine converts a given resource from acquired for exclusive access to acquired for shared access.

## -parameters

### -param Resource 

[in, out]
A pointer to the resource for which the access should be converted.

## -remarks

The caller must have exclusive access to the given resource. During this conversion, the current thread and any other threads waiting for shared access to the resource are given shared access.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exisresourceacquiredexclusivelite">ExIsResourceAcquiredExclusiveLite</a>