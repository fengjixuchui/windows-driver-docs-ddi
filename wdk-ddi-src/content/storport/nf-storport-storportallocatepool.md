---
UID: NF:storport.StorPortAllocatePool
title: StorPortAllocatePool function (storport.h)
description: The StorPortAllocatePool routine allocates a block of non-contiguous, non-paged pool memory.
old-location: storage\storportallocatepool.htm
tech.root: storage
ms.assetid: e6823b9c-9717-49ab-8e67-c1d522774826
ms.date: 07/19/2019
ms.keywords: StorPortAllocatePool, StorPortAllocatePool routine [Storage Devices], storage.storportallocatepool, storport/StorPortAllocatePool, storprt_4ede181d-6ccf-47af-974d-b0daaa6e723a.xml
ms.topic: function
f1_keywords:
 - "storport/StorPortAllocatePool"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StorPortAllocatePool2, StorPortIrql
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- storport.h
api_name:
- StorPortAllocatePool
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortAllocatePool function

## -description

The **StorPortAllocatePool** routine allocates a block of non-contiguous, non-paged pool memory.

## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).

### -param NumberOfBytes [in]

The size, in bytes, of the block of memory being allocated.

### -param Tag [in]

The pool tag for the allocated memory. Drivers specify the pool tag as a string of four ASCII characters, delimited by single quotation marks. The string is usually specified in reverse order.

### -param BufferPointer [out]

A pointer to the address of the allocated memory block or **NULL** if not successful.

## -returns

StorPortAllocatePool returns one of the following status codes:

| Return code | Description |
| ----------- | ----------- |
| **STOR_STATUS_NOT_IMPLEMENTED** | This function is not implemented on the active operating system. |
| **STOR_STATUS_SUCCESS** | Indicates that the routine successfully allocated a memory block of the requested size. |
| **STOR_STATUS_INVALID_PARAMETER** | The pointer to receive the buffer address is **NULL**. |
| **STOR_STATUS_INVALID_IRQL** | The call was made at an invalid IRQL. |
| **STOR_STATUS_INSUFFICIENT_RESOURCES** | Unable to allocate memory of the requested size. |

## -remarks

A miniport driver calls the **StorPortAllocatePool** routine to allocate a block of non-contiguous memory from the non-paged pool. To free the block of memory, the miniport driver calls [**StorPortFreePool**](https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportfreepool). If the request fails, *BufferPointer* will be set to **NULL**.

## -see-also

[**StorPortFreePool**](https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportfreepool)