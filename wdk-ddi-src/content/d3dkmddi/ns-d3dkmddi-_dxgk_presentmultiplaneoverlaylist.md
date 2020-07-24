---
UID: NS:d3dkmddi._DXGK_PRESENTMULTIPLANEOVERLAYLIST
title: _DXGK_PRESENTMULTIPLANEOVERLAYLIST (d3dkmddi.h)
description: Specifies an overlay plane to display in a call to the DxgkDdiPresent function.
old-location: display\dxgk_presentmultiplaneoverlaylist.htm
ms.assetid: 970b3155-9e81-4725-90ee-079339c1d5c5
ms.date: 05/10/2018
keywords: ["_DXGK_PRESENTMULTIPLANEOVERLAYLIST structure"]
ms.keywords: DXGK_PRESENTMULTIPLANEOVERLAYLIST, DXGK_PRESENTMULTIPLANEOVERLAYLIST structure [Display Devices], _DXGK_PRESENTMULTIPLANEOVERLAYLIST, d3dkmddi/DXGK_PRESENTMULTIPLANEOVERLAYLIST, display.dxgk_presentmultiplaneoverlaylist
f1_keywords:
 - "d3dkmddi/DXGK_PRESENTMULTIPLANEOVERLAYLIST"
 - "DXGK_PRESENTMULTIPLANEOVERLAYLIST"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
- D3dkmddi.h
api_name:
- DXGK_PRESENTMULTIPLANEOVERLAYLIST
targetos: Windows
tech.root: display
req.typenames: DXGK_PRESENTMULTIPLANEOVERLAYLIST
---

# _DXGK_PRESENTMULTIPLANEOVERLAYLIST structure


## -description


Specifies an overlay plane to display in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_present">DxgkDdiPresent</a> function.


## -struct-fields




### -field LayerIndex

The zero-based index of the overlay plane to display. The top plane (in the z-direction) has index zero. The planes' index values must be sequential from top to bottom.


### -field Enabled

Indicates whether the overlay plane specified by <b>LayerIndex</b> is enabled for display.


### -field hDeviceSpecificAllocation

A handle to the device-specific allocation that corresponds to the non device-specific allocation. The display miniport driver must set <b>hDeviceSpecificAllocation</b> to a handle value that it can use to refer to its private tracking structure for the allocation.


### -field SegmentId

[in] The identifier of a segment that data is read from.


### -field Reserved

This member is reserved and should be set to zero.


### -field PhysicalAddress

[in] A <b>PHYSICAL_ADDRESS</b> data type (which is defined as <b>LARGE_INTEGER</b>) that indicates the physical address, within the segment that <b>SegmentId</b> specifies, where the data is read.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_present">DxgkDdiPresent</a>
 

 

