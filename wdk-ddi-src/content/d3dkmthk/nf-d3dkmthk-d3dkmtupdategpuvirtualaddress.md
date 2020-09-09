---
UID: NF:d3dkmthk.D3DKMTUpdateGpuVirtualAddress
title: D3DKMTUpdateGpuVirtualAddress function (d3dkmthk.h)
description: D3DKMTUpdateGpuVirtualAddress is a special operation used in the context of tile resources. It allows the driver to specify a number of mapping operations to be applied to the process virtual address space in a single batch of page table updates.
old-location: display\d3dkmtupdategpuvirtualaddress.htm
ms.assetid: 3390A01D-BD4B-4399-AA3E-91BB32264A13
ms.date: 05/10/2018
keywords: ["D3DKMTUpdateGpuVirtualAddress function"]
ms.keywords: D3DKMTUpdateGpuVirtualAddress, D3DKMTUpdateGpuVirtualAddress function [Display Devices], d3dkmthk/D3DKMTUpdateGpuVirtualAddress, display.d3dkmtupdategpuvirtualaddress
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTUpdateGpuVirtualAddress
 - d3dkmthk/D3DKMTUpdateGpuVirtualAddress
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - API-MS-Win-DX-D3DKMT-L1-1-1.dll
 - GDI32.dll
 - API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
 - D3DKMTUpdateGpuVirtualAddress
---

# D3DKMTUpdateGpuVirtualAddress function


## -description

<b>D3DKMTUpdateGpuVirtualAddress</b> is a special operation used in the context of tile resources. It allows the driver to specify a number of mapping operations to be applied to the process virtual address space in a single batch of page table updates.

## -parameters

### -param D3DKMT_UPDATEGPUVIRTUALADDRESS

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_updategpuvirtualaddress">D3DKMT_UPDATEGPUVIRTUALADDRESS</a> structure that describes the operation.

## -returns

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The device context was successfully created.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
 
This function might also return other <b>NTSTATUS</b> values.

## -remarks

The range of graphics processing unit (GPU) virtual addresses in all operations (except the source of the copy operations) must belong to a single virtual address range which was obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_reservegpuvirtualaddressrange">ReserveGpuVirtualAddressRange</a>.   Similarly, the virtual address ranges of all sources in copy operations must belong to a single virtual address range, which was obtained by calling <i>ReserveGpuVirtualAddressRange</i>.

The page table updates are executed on a paging context, dedicated to the rendering context specified, and executed on the GPU only after the associated rendering context signaled <b>FenceValue</b> for the specified monitored fence object. When the page table updates are finished, the paging context signals the monitored fence object to <b>FenceValue</b>+1, allowing the rendering context to do tight interlocking with the page table updates.

The virtual address ranges in the update operations are allowed to intersect. The operations will be applied in the order they are submitted.

In a single <b>UpdateVirtualAddress</b> call:

<ul>
<li>All virtual address ranges in mapping operations and the destination range in copy operations must belong to the same reserved (zero) range.</li>
<li>The source virtual address range in copy operations is allowed to be from a different reserved (zero) range.</li>
<li>The source virtual address range in all copy operations must belong to the same reserved (zero) range.</li>
</ul>

Drivers can submit many <b>UpdateGpuVirtualAddress</b> calls, which will be queued behind the rendering fence. When the number of queued update operations exceeds 128, the calling thread will be blocked until the pervious operations are processed by the video memory manager.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_updategpuvirtualaddress">D3DKMT_UPDATEGPUVIRTUALADDRESS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_reservegpuvirtualaddressrange">ReserveGpuVirtualAddressRange</a>

