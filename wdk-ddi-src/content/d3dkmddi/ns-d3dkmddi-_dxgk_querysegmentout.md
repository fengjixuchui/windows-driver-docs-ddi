---
UID: NS:d3dkmddi._DXGK_QUERYSEGMENTOUT
title: _DXGK_QUERYSEGMENTOUT (d3dkmddi.h)
description: The DXGK_QUERYSEGMENTOUT structure describes memory-segment information that the display miniport driver should return from a call to its DxgkDdiQueryAdapterInfo function.
old-location: display\dxgk_querysegmentout.htm
ms.assetid: df640b7a-865a-4a8b-94be-ebc60e44cf72
ms.date: 05/10/2018
keywords: ["_DXGK_QUERYSEGMENTOUT structure"]
ms.keywords: DXGK_QUERYSEGMENTOUT, DXGK_QUERYSEGMENTOUT structure [Display Devices], DmStructs_69650838-cd41-4786-aa3c-b2617b7d97b4.xml, _DXGK_QUERYSEGMENTOUT, d3dkmddi/DXGK_QUERYSEGMENTOUT, display.dxgk_querysegmentout
f1_keywords:
 - "d3dkmddi/DXGK_QUERYSEGMENTOUT"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGK_QUERYSEGMENTOUT
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_QUERYSEGMENTOUT
---

# _DXGK_QUERYSEGMENTOUT structure


## -description


The DXGK_QUERYSEGMENTOUT structure describes memory-segment information that the display miniport driver should return from a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a> function. 


## -struct-fields




### -field NbSegment

[out] The number of memory segments that the driver supports.


### -field pSegmentDescriptor

[out] An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_segmentdescriptor">DXGK_SEGMENTDESCRIPTOR</a> structures that the driver populates with information about the segments it supports. The size of the array is the value that <b>NbSegment</b> specifies.


### -field PagingBufferSegmentId

[out] The identifier of the segment that the video memory manager should allocate the paging buffer from. This segment must be an aperture segment.


### -field PagingBufferSize

[out] The size, in bytes, that the video memory manager should allocate for the paging buffer.


### -field PagingBufferPrivateDataSize

[out] The size, in bytes, of the driver-resident private data structure that is associated with each paging buffer. Memory for this private data structure is allocated from nonpaged pool. If the driver specifies zero for <b>PagingBufferPrivateDataSize</b>, no memory is allocated for the private data structure.

The private data structure that is associated with a paging buffer is initialized to zero when the paging buffer is created. During the lifetime of the paging buffer, the video memory manager never accesses the private data structure that is associated with the paging buffer.


## -remarks



The video memory manager allocates a paging buffer either from an aperture segment (if the <b>PagingBufferSegmentId</b> member identifies the segment) or as a contiguous write-combined memory block (if <b>PagingBufferSegmentId</b> is set to 0). If <b>PagingBufferSegmentId</b> is set to 0, the graphics processing unit (GPU) must access direct memory access (DMA) buffers by using PCI cycles on systems where AGP transfers that occur outside the AGP aperture are not permitted.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_querysegmentin">DXGK_QUERYSEGMENTIN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_segmentdescriptor">DXGK_SEGMENTDESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a>
 

 

