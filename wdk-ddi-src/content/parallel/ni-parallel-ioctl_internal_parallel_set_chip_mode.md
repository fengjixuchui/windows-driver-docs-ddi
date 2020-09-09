---
UID: NI:parallel.IOCTL_INTERNAL_PARALLEL_SET_CHIP_MODE
title: IOCTL_INTERNAL_PARALLEL_SET_CHIP_MODE (parallel.h)
description: The IOCTL_INTERNAL_PARALLEL_SET_CHIP_MODE request sets the operating mode of a parallel port.
old-location: parports\ioctl_internal_parallel_set_chip_mode.htm
tech.root: parports
ms.assetid: c6bf2f5a-1682-4437-93b1-1a7e5794befd
ms.date: 02/15/2018
keywords: ["IOCTL_INTERNAL_PARALLEL_SET_CHIP_MODE IOCTL"]
ms.keywords: IOCTL_INTERNAL_PARALLEL_SET_CHIP_MODE, IOCTL_INTERNAL_PARALLEL_SET_CHIP_MODE control code [Parallel Ports], cisspd_f9ea9799-8d87-44e2-89d6-ae1fc0a4f673.xml, parallel/IOCTL_INTERNAL_PARALLEL_SET_CHIP_MODE, parports.ioctl_internal_parallel_set_chip_mode
req.header: parallel.h
req.include-header: Parallel.h
req.target-type: Windows
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
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
f1_keywords:
 - IOCTL_INTERNAL_PARALLEL_SET_CHIP_MODE
 - parallel/IOCTL_INTERNAL_PARALLEL_SET_CHIP_MODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - parallel.h
api_name:
 - IOCTL_INTERNAL_PARALLEL_SET_CHIP_MODE
---

# IOCTL_INTERNAL_PARALLEL_SET_CHIP_MODE IOCTL


##  Major Code:


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)


## -description

The <b>IOCTL_INTERNAL_PARALLEL_SET_CHIP_MODE</b> request sets the operating mode of a parallel port.

For more information, see <a href="https://docs.microsoft.com/previous-versions/ff544801(v=vs.85)">Setting and Clearing the Communication Mode on a ParallelPort</a>.

## -ioctlparameters

### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a <a href="..\parallel\ns-parallel-_parallel_chip_mode.md">PARALLEL_CHIP_MODE</a> structure that the client allocates to input chip mode information. The client sets the <b>ChipMode</b> member to the requested operating mode.

### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a PARALLEL_CHIP_MODE structure.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel ports or to one of the following values:




**STATUS_BUFFER_TOO_SMALL**

The value of the <b>Parameters.DeviceIoControl.InputBufferLength</b> member is less than the size, in bytes, of a PARALLEL_CHIP_MODE structure.


**STATUS_INVALID_DEVICE_STATE**

The mode is not cleared.


**STATUS_NO_SUCH_DEVICE**

The requested operating mode is not valid.

## -see-also

<a href="..\parallel\ni-parallel-ioctl_internal_parallel_clear_chip_mode.md">IOCTL_INTERNAL_PARALLEL_CLEAR_CHIP_MODE</a>



<a href="..\parallel\ns-parallel-_parallel_chip_mode.md">PARALLEL_CHIP_MODE</a>

