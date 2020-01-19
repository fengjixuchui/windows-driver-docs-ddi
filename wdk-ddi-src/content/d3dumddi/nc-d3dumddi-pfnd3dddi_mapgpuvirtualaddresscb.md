---
UID: NC:d3dumddi.PFND3DDDI_MAPGPUVIRTUALADDRESSCB
title: PFND3DDDI_MAPGPUVIRTUALADDRESSCB (d3dumddi.h)
description: pfnMapGpuVirtualAddressCb maps graphics processing unit (GPU) virtual address ranges to a specific allocation range or puts it to the Invalid or Zero state.
old-location: display\pfnmapgpuvirtualaddresscb.htm
tech.root: display
ms.assetid: DA67A98C-BE9C-412D-9382-CAC5B05FEE3B
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_MAPGPUVIRTUALADDRESSCB, PFND3DDDI_MAPGPUVIRTUALADDRESSCB callback, d3dumddi/pfnMapGpuVirtualAddressCb, display.pfnmapgpuvirtualaddresscb, pfnMapGpuVirtualAddressCb, pfnMapGpuVirtualAddressCb callback function [Display Devices]
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - "d3dumddi/pfnMapGpuVirtualAddressCb"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - pfnMapGpuVirtualAddressCb
product:
 - Windows
---

# PFND3DDDI_MAPGPUVIRTUALADDRESSCB callback function

## -description

<b>pfnMapGpuVirtualAddressCb</b> maps graphics processing unit (GPU) virtual address ranges to a specific allocation range or puts it to the <i>Invalid</i> or <i>Zero</i> state. The user mode driver can specify a specific base GPU virtual address to map or let the video memory manager automatically pick one. 
When specifying a non-NULL <b>BaseAddress</b> value, the entire range from <b>BaseAddress</b> to <b>BaseAddress</b>+<b>Size</b> must be in a freed state or belong to a virtual address range, obtained by calling <b>pfnMapGpuVirtualAddressCb</b> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_reservegpuvirtualaddresscb">pfnReserveGpuVirtualAddressCb</a>. Note that when <b>Protection.Zero</b> or <b>Protection.NoAccess</b> is specified, the virtual address range cannot belong to a range, obtained by calling <b>pfnMapGpuVirtualAddressCb</b>.
The user mode driver  may specify if the mapping should allow for write & execute privileges in addition to read privileges, which always exist by default. 
In LDA configuration the paging queue defines a physical GPU, whose page tables are modified, and the allocation handle (if not NULL) defines where the page table entries are pointing to. The allocation can be resident in any physical GPU memory segment.

## -parameters

### -param hDevice

A handle to the display device.

### -param Arg2

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-d3dddi_mapgpuvirtualaddress">D3DDDI_MAPGPUVIRTUALADDRESS</a> structure that describes the operation to perform.

## -returns

<b>pfnMapGpuVirtualAddressCb</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The operation completed successfully.|
|E_PENDING|The call was successful, but the operation is not finished. The caller must wait for the returned fence value before accessing the allocation.|

This function might also return other values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-d3dddi_mapgpuvirtualaddress">D3DDDI_MAPGPUVIRTUALADDRESS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_reservegpuvirtualaddresscb">pfnReserveGpuVirtualAddressCb</a>

