---
UID: NE:d3dkmdt._D3DKMDT_VIDPN_PRESENT_PATH_SCALING
title: _D3DKMDT_VIDPN_PRESENT_PATH_SCALING (d3dkmdt.h)
description: The D3DKMDT_VIDPN_PRESENT_PATH_SCALING enumeration is used to indicate the scaling transformation applied to content displayed on a VidPN present path.
old-location: display\d3dkmdt_vidpn_present_path_scaling.htm
tech.root: display
ms.assetid: 4453534e-ce2b-4b0d-a93d-3d17185083fd
ms.date: 05/10/2018
ms.keywords: D3DKMDT_VIDPN_PRESENT_PATH_SCALING, D3DKMDT_VIDPN_PRESENT_PATH_SCALING enumeration [Display Devices], D3DKMDT_VPPS_ASPECTRATIOCENTEREDMAX, D3DKMDT_VPPS_CENTERED, D3DKMDT_VPPS_CUSTOM, D3DKMDT_VPPS_IDENTITY, D3DKMDT_VPPS_NOTSPECIFIED, D3DKMDT_VPPS_RESERVED1, D3DKMDT_VPPS_STRETCHED, D3DKMDT_VPPS_UNINITIALIZED, D3DKMDT_VPPS_UNPINNED, DmEnums_a2e5faad-ade2-4a1d-b096-f221bf0bdf20.xml, _D3DKMDT_VIDPN_PRESENT_PATH_SCALING, d3dkmdt/D3DKMDT_VIDPN_PRESENT_PATH_SCALING, d3dkmdt/D3DKMDT_VPPS_ASPECTRATIOCENTEREDMAX, d3dkmdt/D3DKMDT_VPPS_CENTERED, d3dkmdt/D3DKMDT_VPPS_CUSTOM, d3dkmdt/D3DKMDT_VPPS_IDENTITY, d3dkmdt/D3DKMDT_VPPS_NOTSPECIFIED, d3dkmdt/D3DKMDT_VPPS_RESERVED1, d3dkmdt/D3DKMDT_VPPS_STRETCHED, d3dkmdt/D3DKMDT_VPPS_UNINITIALIZED, d3dkmdt/D3DKMDT_VPPS_UNPINNED, display.d3dkmdt_vidpn_present_path_scaling
ms.topic: enum
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
- D3DKMDT_VIDPN_PRESENT_PATH_SCALING
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_VIDPN_PRESENT_PATH_SCALING
---

# _D3DKMDT_VIDPN_PRESENT_PATH_SCALING enumeration


## -description


The D3DKMDT_VIDPN_PRESENT_PATH_SCALING enumeration is used to indicate the scaling transformation applied to content displayed on a VidPN present path.


## -enum-fields




### -field D3DKMDT_VPPS_UNINITIALIZED

Indicates that a variable of type D3DKMDT_VIDPN_PRESENT_PATH_SCALING has not yet been assigned a meaningful value.


### -field D3DKMDT_VPPS_IDENTITY

Indicates the identity transformation; the source content is presented with no change. Note that this transformation is available only if the path's source mode has the same spatial resolution as the path's target mode.


### -field D3DKMDT_VPPS_CENTERED

Indicates the centering transformation; the source content is presented unscaled, centered with respect to the spatial resolution of the target mode.


### -field D3DKMDT_VPPS_STRETCHED

Indicates that the source content is scaled to fit the path's target, and the aspect ratio of the source is not preserved.


### -field D3DKMDT_VPPS_ASPECTRATIOCENTEREDMAX

Indicates that the source content is scaled to fit the path's target while preserving the aspect ratio of the source.

This constant value is available beginning with Windows 7. See further information in the Remarks section.


### -field D3DKMDT_VPPS_CUSTOM

Indicates that the path is capable of displaying one or more scaling modes that are not described by other constants of this enumeration.

This constant value is available beginning with Windows 7. See further information in the Remarks section.


### -field D3DKMDT_VPPS_RESERVED1

Reserved for system use. Do not use this value. This value will never be passed to a driver.

This constant value is available beginning with Windows 7.


### -field D3DKMDT_VPPS_UNPINNED

Indicates that no scaling transformation has been pinned for the VidPN present source.


### -field D3DKMDT_VPPS_NOTSPECIFIED

Indicates that no transformation has been specified. See further information in the Remarks section.


## -remarks



The <b>Scaling</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path_transformation">D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION</a> structure is a value from the D3DKMDT_VIDPN_PRESENT_PATH_SCALING enumeration.

If D3DKMDT_VPPS_ASPECTRATIOCENTEREDMAX or D3DKMDT_VPPS_CUSTOM values are specified but the path is on a display miniport driver that does not support these values (which are available beginning with Windows 7), the driver's calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_commitvidpn">DxgkDdiCommitVidPn</a> should return STATUS_GRAPHICS_VIDPN_MODALITY_NOT_SUPPORTED, and the operating system will apply the system default scaling. If a driver cannot support the requested scaling value on the specified path, its calls to <b>DxgkDdiCommitVidPn</b> should return STATUS_GRAPHICS_VIDPN_MODALITY_NOT_SUPPORTED.

<div class="alert"><b>Note</b>    A display miniport driver that supports the D3DKMDT_VPPS_ASPECTRATIOCENTEREDMAX or D3DKMDT_VPPS_CUSTOM values should never set a value of D3DKMDT_VPPS_NOTSPECIFIED.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path_scaling_support">D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_commitvidpn">DxgkDdiCommitVidPn</a>
 

 

