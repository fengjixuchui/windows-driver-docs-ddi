---
UID: NS:d3dkmdt._D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION
title: _D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION (d3dkmdt.h)
description: The D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION structure contains information about the transformations (for example, rotation, scaling, centering) that are pinned and the transformations that are supported for a path in a video present network (VIDPN).
old-location: display\d3dkmdt_vidpn_present_path_transformation.htm
tech.root: display
ms.assetid: 7b2370c8-ea8a-4719-b88a-2401dbafb64c
ms.date: 05/10/2018
keywords: ["_D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION structure"]
ms.keywords: D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION, D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION structure [Display Devices], DmStructs_3c1dd0fd-471f-48e0-9df5-003f98237ac2.xml, _D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION, d3dkmdt/D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION, display.d3dkmdt_vidpn_present_path_transformation
f1_keywords:
 - "d3dkmdt/D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION"
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
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
- d3dkmdt.h
api_name:
- D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION
---

# _D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION structure


## -description


The <b>D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION</b> structure contains information about the transformations (for example, rotation, scaling, centering) that are pinned and the transformations that are supported for a path in a video present network (VIDPN).


## -struct-fields




### -field Scaling

A value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_vidpn_present_path_scaling">D3DKMDT_VIDPN_PRESENT_PATH_SCALING</a> enumeration that indicates the type of scaling (or centering) that is currently set for the path. If this member is equal to <b>D3DKMDT_VPPS_IDENTITY</b>, <b>D3DKMDT_VPPS_CENTERED</b>, <b>D3DKMDT_VPPS_STRETCHED</b>, <b>D3DKMDT_VPPS_ASPECTRATIOCENTEREDMAX</b>, or <b>D3DKMDT_VPPS_CUSTOM</b>, then the indicated scaling type is considered pinned for the path. If this member is equal to any other value, then no scaling type is pinned for the path.

For more information on how to use this member, see the Remarks section.


### -field ScalingSupport

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path_scaling_support">D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT</a> structure that holds a set of flags that indicate the types of scaling that are supported by the path.


### -field Rotation

A value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_vidpn_present_path_rotation">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a> enumeration that indicates the type of rotation that is currently set for the path. If this member is equal to <b>D3DKMDT_VPPR_IDENTITY</b>, <b>D3DKMDT_VPPR_ROTATE90</b>, <b>D3DKMDT_VPPR_ROTATE180</b> or <b>D3DKMDT_VPPR_ROTATE270</b>, then the indicated rotation type is considered pinned for the path. If this member is equal to any other value, then no rotation type is pinned for the path.


### -field RotationSupport

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path_rotation_support">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT</a> structure that holds a set of flags that indicate the types of rotation that are supported by the path.


## -remarks



The <b>ContentTransformation</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a> structure is a  <b>D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION</b> structure.

If <b>D3DKMDT_VPPS_ASPECTRATIOCENTEREDMAX</b> or <b>D3DKMDT_VPPS_CUSTOM</b> values are specified in the <b>Scaling</b> member but the path is on a display miniport driver that does not support these values (which are available beginning with Windows 7), the driver's calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_commitvidpn">DxgkDdiCommitVidPn</a> should return <b>STATUS_GRAPHICS_VIDPN_MODALITY_NOT_SUPPORTED</b>, and the operating system will apply the system default scaling. If a driver cannot support the requested scaling value on the specified path, its calls to <b>DxgkDdiCommitVidPn</b> should return <b>STATUS_GRAPHICS_VIDPN_MODALITY_NOT_SUPPORTED</b>.

<div class="alert"><b>Note</b>    A display miniport driver that supports the <b>D3DKMDT_VPPS_ASPECTRATIOCENTEREDMAX</b> or <b>D3DKMDT_VPPS_CUSTOM</b> values should never set a value of <b>D3DKMDT_VPPS_NOTSPECIFIED</b>.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_vidpn_present_path_rotation">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path_rotation_support">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_d3dkmdt_vidpn_present_path_scaling">D3DKMDT_VIDPN_PRESENT_PATH_SCALING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path_scaling_support">D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_commitvidpn">DxgkDdiCommitVidPn</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality">DxgkDdiEnumVidPnCofuncModality</a>
 

 

