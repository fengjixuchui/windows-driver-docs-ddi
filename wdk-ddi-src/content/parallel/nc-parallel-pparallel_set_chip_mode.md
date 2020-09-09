---
UID: NC:parallel.PPARALLEL_SET_CHIP_MODE
title: PPARALLEL_SET_CHIP_MODE (parallel.h)
description: The PPARALLEL_SET_CHIP_MODE-typed callback routine sets the operating mode of a parallel port. The system-supplied function driver for parallel ports supplies this routine.
old-location: parports\pparallel_set_chip_mode.htm
tech.root: parports
ms.assetid: 7c80f3ee-cbb2-400d-9dfb-36ccef93d80f
ms.date: 02/15/2018
keywords: ["PPARALLEL_SET_CHIP_MODE callback"]
ms.keywords: "(*PPARALLEL_SET_CHIP_MODE), (*PPARALLEL_SET_CHIP_MODE) callback function [Parallel Ports], cisspd_a108ba77-8f01-436e-bc7a-48a74f80ac75.xml, parallel/(*PPARALLEL_SET_CHIP_MODE), parports.pparallel_set_chip_mode"
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
 - PPARALLEL_SET_CHIP_MODE
 - parallel/PPARALLEL_SET_CHIP_MODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - parallel.h
api_name:
 - (*PPARALLEL_SET_CHIP_MODE)
---

# PPARALLEL_SET_CHIP_MODE callback


## -description

The <i>PPARALLEL_SET_CHIP_MODE</i>-typed callback routine sets the operating mode of a parallel port. The system-supplied function driver for parallel ports supplies this routine.

## -parameters

### -param SetChipContext 

[in]
Pointer to the device extension of a parallel port's functional device object (<a href="https://docs.microsoft.com/windows-hardware/drivers/">FDO</a>).

### -param ChipMode 

[in]
Specifies the operating mode of a parallel port. (For more information about operating modes, see the modes that are defined for the enhanced capabilities register (ECR) in the <i>parallel.h</i> file that is included in the Microsoft Windows Driver Kit [WDK].)

## -returns

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The specified operating mode was set.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>
</td>
<td width="60%">
The mode is not cleared.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_SUCH_DEVICE</b></dt>
</dl>
</td>
<td width="60%">
The specified operating mode is not valid.

</td>
</tr>
</table>

## -prototype

```cpp
typedef NTSTATUS (*PPARALLEL_SET_CHIP_MODE)(
  _In_ PVOID SetChipContext,
  _In_ UCHAR ChipMode
);
```

## -remarks

To obtain a pointer to the system-supplied <i>PPARALLEL_SET_CHIP_MODE</i> callback, a kernel-mode driver uses an <a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_pnp_info.md">IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO</a> request, which returns a <a href="..\parallel\ns-parallel-_parallel_pnp_information.md">PARALLEL_PNP_INFORMATION</a> structure. The <b>TrySetChipMode</b> member of the PARALLEL_PNP_INFORMATION structure is a pointer to this callback.

A caller uses the <i>PPARALLEL_SET_CHIP_MODE</i> callback in conjunction with the <a href="..\parallel\nc-parallel-pparallel_clear_chip_mode.md">PPARALLEL_CLEAR_CHIP_MODE</a> callback.

To set a new mode, a caller must first clear the current mode.

For more information, see <a href="https://docs.microsoft.com/previous-versions/ff544801(v=vs.85)">Setting and Clearing the Communication Mode on a ParallelPort</a>.

## -see-also

<a href="..\parallel\ni-parallel-ioctl_internal_parallel_set_chip_mode.md">IOCTL_INTERNAL_PARALLEL_SET_CHIP_MODE</a>



<a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_port_info.md">IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO</a>



<a href="..\parallel\ns-parallel-_parallel_pnp_information.md">PARALLEL_PNP_INFORMATION</a>



<a href="..\parallel\ni-parallel-ioctl_internal_parallel_clear_chip_mode.md">IOCTL_INTERNAL_PARALLEL_CLEAR_CHIP_MODE</a>



<a href="..\parallel\nc-parallel-pparallel_clear_chip_mode.md">PPARALLEL_CLEAR_CHIP_MODE</a>

