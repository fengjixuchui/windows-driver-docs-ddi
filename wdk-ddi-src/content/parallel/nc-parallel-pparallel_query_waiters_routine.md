---
UID: NC:parallel.PPARALLEL_QUERY_WAITERS_ROUTINE
title: PPARALLEL_QUERY_WAITERS_ROUTINE (parallel.h)
description: The PPARALLEL_QUERY_WAITERS_ROUTINE-typed callback routine returns the number of IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE and IOCTL_INTERNAL_SELECT_DEVICE requests that are queued on the work queue of a parallel port.
old-location: parports\pparallel_query_waiters_routine.htm
tech.root: parports
ms.assetid: 0fe598b9-2143-4981-b562-6b0f135ec770
ms.date: 02/15/2018
keywords: ["PPARALLEL_QUERY_WAITERS_ROUTINE callback"]
ms.keywords: "(*PPARALLEL_QUERY_WAITERS_ROUTINE), (*PPARALLEL_QUERY_WAITERS_ROUTINE) callback function [Parallel Ports], cisspd_d1e6d424-75ec-4cc1-b144-05900a24a684.xml, parallel/(*PPARALLEL_QUERY_WAITERS_ROUTINE), parports.pparallel_query_waiters_routine"
req.header: parallel.h
req.include-header: Parallel.h
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
f1_keywords:
 - PPARALLEL_QUERY_WAITERS_ROUTINE
 - parallel/PPARALLEL_QUERY_WAITERS_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - parallel.h
api_name:
 - (*PPARALLEL_QUERY_WAITERS_ROUTINE)
---

# PPARALLEL_QUERY_WAITERS_ROUTINE callback


## -description

The <i>PPARALLEL_QUERY_WAITERS_ROUTINE</i>-typed callback routine returns the number of <a href="..\parallel\ni-parallel-ioctl_internal_parallel_port_allocate.md">IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE</a> and <a href="..\parallel\ni-parallel-ioctl_internal_select_device.md">IOCTL_INTERNAL_SELECT_DEVICE</a> requests that are queued on the work queue of a parallel port. The system-supplied function driver for parallel ports supplies this routine.

## -parameters

### -param QueryAllocsContext 

[in]
Pointer to the device extension of a functional device object (<a href="https://docs.microsoft.com/windows-hardware/drivers/">FDO</a>) that represents a parallel port.

## -returns

The number of requests that are queued on the work queue of the parallel port.

## -prototype

```cpp
typedef ULONG (*PPARALLEL_QUERY_WAITERS_ROUTINE)(
  _In_ PVOID QueryAllocsContext
);
```

## -remarks

To obtain a pointer to the system-supplied <i>PPARALLEL_QUERY_WAITERS_ROUTINE</i> callback, a kernel-mode driver uses an <a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_port_info.md">IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO</a> request, which returns a <a href="..\parallel\ns-parallel-_parallel_port_information.md">PARALLEL_PORT_INFORMATION</a> structure. The <b>QueryNumWaiters</b> member of the PARALLEL_PORT_INFORMATION structure is a pointer to this callback.

A driver can use the <i>PPARALLEL_QUERY_WAITERS_ROUTINE</i> callback to adjust its use of the parallel port based on the number of other clients that are waiting for access to the parallel port. The system-supplied function driver for parallel ports queues only allocate and select requests.

For more information, see <a href="https://docs.microsoft.com/previous-versions/ff544809(v=vs.85)">Synchronizing the Use of a ParallelPort</a>.

## -see-also

<a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_port_info.md">IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO</a>



<a href="..\parallel\ni-parallel-ioctl_internal_parallel_port_allocate.md">IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE</a>



<a href="..\parallel\nc-parallel-pparallel_free_routine.md">PPARALLEL_FREE_ROUTINE</a>



<a href="..\parallel\ni-parallel-ioctl_internal_parallel_port_free.md">IOCTL_INTERNAL_PARALLEL_PORT_FREE</a>



<a href="..\parallel\ns-parallel-_parallel_port_information.md">PARALLEL_PORT_INFORMATION</a>

