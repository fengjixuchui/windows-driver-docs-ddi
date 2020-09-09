---
UID: NF:ndis.NdisFillMemory
title: NdisFillMemory macro (ndis.h)
description: The NdisFillMemory function fills a caller-supplied buffer with the given character.
old-location: netvista\ndisfillmemory.htm
tech.root: netvista
ms.assetid: 6d974c56-5925-4ad5-a3c0-0c17e8488431
ms.date: 05/02/2018
keywords: ["NdisFillMemory macro"]
ms.keywords: NdisFillMemory, NdisFillMemory macro [Network Drivers Starting with Windows Vista], ndis/NdisFillMemory, ndis_memory_ref_c1411624-0e7b-40e2-9812-4426b2a9f2bc.xml, netvista.ndisfillmemory
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlFillMemory instead.
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
req.irql: See Remarks section
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisFillMemory
 - ndis/NdisFillMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NdisFillMemory
---

# NdisFillMemory macro


## -description

The 
  <b>NdisFillMemory</b> function fills a caller-supplied buffer with the given character.

## -parameters

### -param Destination 

[in]
A pointer to the buffer to be filled.

### -param Length 

[in]
The number of bytes to be filled.

### -param Fill 

[in]
The value to fill the buffer.

## -remarks

Callers of 
    <b>NdisFillMemory</b> can be running at any IRQL, provided that the 
    <i>Destination</i> buffer is resident. If the buffer is pageable, a caller must be running at IRQL <
    DISPATCH_LEVEL.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlequalmemory">RtlEqualMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlzeromemory">RtlZeroMemory</a>

