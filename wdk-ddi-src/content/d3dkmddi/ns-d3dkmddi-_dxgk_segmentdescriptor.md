---
UID: NS:d3dkmddi._DXGK_SEGMENTDESCRIPTOR
title: _DXGK_SEGMENTDESCRIPTOR (d3dkmddi.h)
description: The DXGK_SEGMENTDESCRIPTOR structure contains information about a segment that the driver supports.
old-location: display\dxgk_segmentdescriptor.htm
ms.assetid: d9d79c58-6ef6-4917-b499-fd5a70dc8829
ms.date: 05/10/2018
keywords: ["DXGK_SEGMENTDESCRIPTOR structure"]
ms.keywords: DXGK_SEGMENTDESCRIPTOR, DXGK_SEGMENTDESCRIPTOR structure [Display Devices], DmStructs_129432bb-660c-4779-9860-dcc97f3a6ee4.xml, _DXGK_SEGMENTDESCRIPTOR, d3dkmddi/DXGK_SEGMENTDESCRIPTOR, display.dxgk_segmentdescriptor
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
tech.root: display
req.typenames: DXGK_SEGMENTDESCRIPTOR
f1_keywords:
 - _DXGK_SEGMENTDESCRIPTOR
 - d3dkmddi/_DXGK_SEGMENTDESCRIPTOR
 - DXGK_SEGMENTDESCRIPTOR
 - d3dkmddi/DXGK_SEGMENTDESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGK_SEGMENTDESCRIPTOR
---

# _DXGK_SEGMENTDESCRIPTOR structure


## -description

The DXGK_SEGMENTDESCRIPTOR structure contains information about a segment that the driver supports.

## -struct-fields

### -field BaseAddress

[out] The base address of the segment, as determined by the graphics processing unit (GPU). The physical address of an allocation that the video memory manager paged in the segment is assigned a GPU address that is offset from the base address that <b>BaseAddress </b>specifies.

The video memory manager ignores the base address of AGP-type aperture segments (where the <b>Agp</b> bit-field flag is specified in the <b>Flags</b> member) and instead uses the actual physical address of the segment within the AGP aperture, as determined on the bus where the GPU is located. In this situation, the driver can use addresses that the video memory manager generated for allocation directly without requiring translation.

### -field CpuTranslatedAddress

[out] The base address of the segment, relative to the bus that the GPU is connected on. For example, when the GPU is connected on the PCI bus, <b>CpuTranslatedAddress </b>is the base address of the usable range that is specified by a PCI base-address register (BAR). The driver specifies this address only if it specifies a CPU-accessible segment by setting the <b>CpuVisible</b> bit-field flag in the <b>Flags</b> member. 

This member is ignored for aperture segments, including the AGP-type aperture segment.  The only exception occurs when the  user-mode display driver has not set up an alternate virtual address for a primary allocation (that is, when the driver has not set <b>UseAlternateVA</b> in the <b>Flags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddicb_lockflags">D3DDDICB_LOCKFLAGS</a> structure during a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb">pfnLockCb</a> function).

Before the video memory manager maps a virtual address to the physical range, the video memory manager translates this physical address based on the CPU view of the bus and informs the driver about the operation so the driver can set up an aperture to access the content of the segment at the given location.

### -field Size

[out] The size, in bytes, of the segment. This size must be a multiple of the native host page size (for example, 4 KB on the x86 architecture).

For AGP-type aperture segments (where the <b>Agp</b> bit-field flag is specified in the <b>Flags</b> member), the video memory manager allocates as much aperture space as possible, so  this member is ignored.

### -field NbOfBanks

[out] The number of banks in the segment, if banking is used (that is, if the <b>UseBanking</b> bit-field flag is set in the <b>Flags</b> member).

### -field pBankRangeTable

[out] An array of values that indicates the ranges that delimit each bank in the segment. The array specifies the end addresses of the first bank through the <i>n</i>âˆ’1 bank (that is, the end offsets into the segment for each bank). Note the following: 

<ul>
<li>
Banks are contiguous.

</li>
<li>
The first bank starts at offset zero of the segment.

</li>
<li>
The last bank ends at the end of the segment, so the driver is not required to specify the end address of the last bank.

</li>
<li>
The driver specifies this array only if it also sets the <b>UseBanking</b> bit-field flag in the <b>Flags</b> member.

</li>
</ul>

### -field CommitLimit

[out] The maximum number of bytes that can be committed to the segment. For a memory segment, the commit limit is always the same as the size of the segment, which is specified in the <b>Size</b> member. For an aperture segment, the driver can limit the amount of memory that can be committed to the segment on systems with small amounts of physical memory.

### -field Flags

[out] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_segmentflags">DXGK_SEGMENTFLAGS</a> structure that identifies properties, in bit-field flags, for the segment.

Note that for an AGP-type aperture segment, the driver must exclusively set the <b>Agp</b> member of the structure in the union that DXGK_SEGMENTFLAGS contains. Although the AGP-type aperture segment is an aperture and is accessible to the CPU, if any other members are set, the adapter fails to initialize.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddicb_lockflags">D3DDDICB_LOCKFLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfo">DXGK_ALLOCATIONINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_querysegmentin">DXGK_QUERYSEGMENTIN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_querysegmentout">DXGK_QUERYSEGMENTOUT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_segmentflags">DXGK_SEGMENTFLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb">pfnLockCb</a>

