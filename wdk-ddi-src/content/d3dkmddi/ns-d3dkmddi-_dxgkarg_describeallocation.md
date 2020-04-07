---
UID: NS:d3dkmddi._DXGKARG_DESCRIBEALLOCATION
title: _DXGKARG_DESCRIBEALLOCATION (d3dkmddi.h)
description: The DXGKARG_DESCRIBEALLOCATION structure describes an existing allocation.
old-location: display\dxgkarg_describeallocation.htm
ms.assetid: fd01ff3b-83b7-43d5-bbc6-6959485edd15
ms.date: 05/10/2018
keywords: ["_DXGKARG_DESCRIBEALLOCATION structure"]
ms.keywords: "*INOUT_PDXGKARG_DESCRIBEALLOCATION, DXGKARG_DESCRIBEALLOCATION, DXGKARG_DESCRIBEALLOCATION structure [Display Devices], DmStructs_73e3d53a-788b-4c88-980c-df0d2038694f.xml, _DXGKARG_DESCRIBEALLOCATION, d3dkmddi/DXGKARG_DESCRIBEALLOCATION, display.dxgkarg_describeallocation"
f1_keywords:
 - "d3dkmddi/DXGKARG_DESCRIBEALLOCATION"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with  Windows Vista.
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
- DXGKARG_DESCRIBEALLOCATION
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGKARG_DESCRIBEALLOCATION
---

# _DXGKARG_DESCRIBEALLOCATION structure


## -description


The DXGKARG_DESCRIBEALLOCATION structure describes an existing allocation.


## -struct-fields




### -field hAllocation

[in] A handle to an allocation that information is requested for. The driver previously returned this handle in the <b>hAllocation</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfo">DXGK_ALLOCATIONINFO</a> structure from a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a> function.


### -field Width

[out] The width of the allocation, in pixels. The driver returns the width value.


### -field Height

[out] The height of the allocation, in pixels. The driver returns the height value.


### -field Format

[out] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the allocation. The driver returns the format value.


### -field MultisampleMethod

[out] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_multisamplingmethod">D3DDDI_MULTISAMPLINGMETHOD</a> structure that describes the multiple-sampling method that is used for the allocation. The driver returns the description.


### -field RefreshRate

[out] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_rational">D3DDDI_RATIONAL</a> structure that indicates the refresh rate that the primary surface was created with, if applicable.


### -field PrivateDriverFormatAttribute

[out] A UINT value that specifies a private format attribute for the allocation. The driver specifies surface format attributes (for example, the pixel layout of a tiled surface) that it otherwise cannot expose to the operating system. 

The operating system uses the information in <b>PrivateDriverFormatAttribute</b> to compare two surfaces. For example, an A8R8B8G8 800x600 surface and an X8R8B8G8 800x600 surface should have the same information in <b>PrivateDriverFormatAttribute</b> if they have the same format attributes, which includes pixel layout. 


### -field Flags

[out] This member is reserved.

Supported starting with Windows 8.


### -field Rotation

[out] This member is reserved.

Supported starting with Windows 8.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_multisamplingmethod">D3DDDI_MULTISAMPLINGMETHOD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_rational">D3DDDI_RATIONAL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddi_rotation">D3DDDI_ROTATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfo">DXGK_ALLOCATIONINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_describeallocationflags">DXGK_DESCRIBEALLOCATIONFLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_describeallocation">DxgkDdiDescribeAllocation</a>
 

 

