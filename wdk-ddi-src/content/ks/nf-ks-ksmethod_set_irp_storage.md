---
UID: NF:ks.KSMETHOD_SET_IRP_STORAGE
title: KSMETHOD_SET_IRP_STORAGE macro (ks.h)
description: This macro returns a pointer to the KSMETHOD_SET in which the method is located.
old-location: stream\ksmethod_set_irp_storage.htm
tech.root: stream
ms.assetid: bc0a309d-305e-400a-b571-7958926dd1dc
ms.date: 04/23/2018
keywords: ["KSMETHOD_SET_IRP_STORAGE macro"]
ms.keywords: KSMETHOD_SET_IRP_STORAGE, KSMETHOD_SET_IRP_STORAGE macro [Streaming Media Devices], ks/KSMETHOD_SET_IRP_STORAGE, ksfunc_d413bf2a-7d63-48c2-9e75-d84cf1344f5c.xml, stream.ksmethod_set_irp_storage
req.header: ks.h
req.include-header: Ks.h
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
req.irql: 
targetos: Windows
req.typenames: 
ms.custom: 19H1
f1_keywords:
 - KSMETHOD_SET_IRP_STORAGE
 - ks/KSMETHOD_SET_IRP_STORAGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSMETHOD_SET_IRP_STORAGE
---

# KSMETHOD_SET_IRP_STORAGE macro


## -description

This macro returns a pointer to the [KSMETHOD_SET](./ns-ks-ksmethod_set.md) in which the method is located.

## -parameters

### -param Irp 

[in]
Specifies the IRP passed to the handler routine.

## -remarks

The pointer to a KSMETHOD_SET structure is extracted from `Irp->Tail.Overlay.DriverContext`. Parameters in **DriverContext** are initialized by [KsMethodHandler](./nf-ks-ksmethodhandler.md) and [KsMethodHandlerWithAllocator](./nf-ks-ksmethodhandlerwithallocator.md).

The macro is defined as follows:

```cpp
#define KSMETHOD_SET_IRP_STORAGE(Irp)   (*(const KSMETHOD_SET**)&(Irp)->Tail.Overlay.DriverContext[0])
```

## -see-also

[KSMETHOD](/previous-versions/ff563398(v=vs.85))

[KSMETHOD_ITEM](./ns-ks-ksmethod_item.md)

[KSMETHOD_SET](./ns-ks-ksmethod_set.md)

[KsFastMethodHandler](./nf-ks-ksfastmethodhandler.md)

[KsMethodHandler](./nf-ks-ksmethodhandler.md)

[KsMethodHandlerWithAllocator](./nf-ks-ksmethodhandlerwithallocator.md)