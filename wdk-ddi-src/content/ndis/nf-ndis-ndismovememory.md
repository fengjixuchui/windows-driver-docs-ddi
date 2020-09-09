---
UID: NF:ndis.NdisMoveMemory
title: NdisMoveMemory macro (ndis.h)
description: The NdisMoveMemory function copies a specified number of bytes from one caller-supplied location to another.
old-location: netvista\ndismovememory.htm
tech.root: netvista
ms.assetid: 1be08720-be44-4e1b-b0ec-b4eb0a2718a0
ms.date: 05/02/2018
keywords: ["NdisMoveMemory macro"]
ms.keywords: NdisMoveMemory, NdisMoveMemory macro [Network Drivers Starting with Windows Vista], ndis/NdisMoveMemory, ndis_memory_ref_19f420d5-3747-48fa-a6c6-d1088449075b.xml, netvista.ndismovememory
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlCopyMemory (not RtlMoveMemory) instead.
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
 - NdisMoveMemory
 - ndis/NdisMoveMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NdisMoveMemory
---

# NdisMoveMemory macro


## -description

The 
  <b>NdisMoveMemory</b> function copies a specified number of bytes from one caller-supplied location to
  another.

## -parameters

### -param Destination 

[out]
A pointer to a system-space buffer that is the destination of the move. This buffer must be at
     least 
     <i>Length</i> bytes in size.

### -param Source 

[in]
A pointer to a system-space buffer from which this function copies the data to the destination
     buffer. This buffer must be at least 
     <i>Length</i> bytes in size.

### -param Length 

[in]
The number of bytes to copy.

## -remarks

Both 
    <i>Source</i> and 
    <i>Destination</i> are virtual addresses.

If either address falls within a range of device memory that was mapped with 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndismmapiospace">NdisMMapIoSpace</a>, a miniport driver should
    call one of the 
    <b>Ndis..MappedMemory</b> functions instead of 
    <b>NdisMoveMemory</b>.

The range specified by 
    <i>Source</i> and 
    <i>Length</i> cannot overlap the 
    <i>Destination</i> range.

Callers of 
    <b>NdisMoveMemory</b> can run at any IRQL if the given 
    <i>Source</i> and 
    <i>Destination</i> are resident. Otherwise, callers must be running at IRQL < DISPATCH_LEVEL, as, for
    example if either address is on the stack.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatememorywithtagpriority">
   NdisAllocateMemoryWithTagPriority</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndismmapiospace">NdisMMapIoSpace</a>

