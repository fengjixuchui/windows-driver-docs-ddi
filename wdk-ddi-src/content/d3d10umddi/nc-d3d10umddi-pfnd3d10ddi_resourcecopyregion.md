---
UID: NC:d3d10umddi.PFND3D10DDI_RESOURCECOPYREGION
title: PFND3D10DDI_RESOURCECOPYREGION (d3d10umddi.h)
description: The ResourceCopyRegion function copies a source subresource region to a location on a destination subresource.
old-location: display\resourcecopyregion.htm
ms.assetid: e782dc8c-e34e-4f96-b6d9-c34d7843ed05
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_RESOURCECOPYREGION callback function"]
ms.keywords: PFND3D10DDI_RESOURCECOPYREGION, PFND3D10DDI_RESOURCECOPYREGION callback, ResourceCopyRegion, ResourceCopyRegion callback function [Display Devices], UserModeDisplayDriverDx10_Functions_8b5cb003-4fa5-4d23-99c4-a8165253907c.xml, d3d10umddi/ResourceCopyRegion, display.resourcecopyregion
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - "d3d10umddi/ResourceCopyRegion"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - ResourceCopyRegion
product:
 - Windows
---

# PFND3D10DDI_RESOURCECOPYREGION callback function

## -description

The <i>ResourceCopyRegion</i> function copies a source subresource region to a location on a destination subresource.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hDstResource* [in]

A handle to the destination resource to copy to.

### -param Arg3

*DstSubresource* [in]

An index that indicates the destination subresource to copy to.

### -param Arg4

*DstX* [in]

The x-coordinate of the destination subresource.

### -param Arg5

*DstY* [in]

The y-coordinate of the destination subresource. For one-dimensional (1-D) subresources, <i>DstY</i> is set to zero.

### -param Arg6

*DstZ* [in]

The z-coordinate of the destination subresource. For one-dimensional (1-D) and two-dimensional (2-D) subresources, <i>DstZ</i> is set to zero.

### -param Arg7

*hSrcResource* [in]

A handle to the source resource to copy from.

### -param Arg8

*SrcSubresource* [in]

An index that indicates the source subresource to copy from.

### -param Arg9

*pSrcBox* [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_ddi_box">D3D10_DDI_BOX</a> structure that specifies a box that fits on either the source or destination subresource. If <i>pSrcBox</i> is <b>NULL</b>, the driver should copy the entire source subresouce to the destination.

If the members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_ddi_box">D3D10_DDI_BOX</a> structure are such that <b>left</b>>=<b>right</b>, <b>top</b>>=<b>bottom</b>, or <b>front</b>>=<b>back</b>, then <i>pSrcBox</i> is considered empty, and <i>ResourceCopyRegion</i> must not perform any copy operation.

## -remarks


The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 


The Microsoft Direct3D runtime calls the user-mode display driver's <i>ResourceCopyRegion</i> function to inform the driver to copy from the specified source subresource region to a location on the specified destination subresource. The source and destination subresources cannot be the same subresource of the same resource. Both source and destination resources must be the same type of resource and must have format types (DXGI_FORMAT-typed values) that are convertible to each other. 

For buffers, all the coordinates must be in bytes; whereas for textures, all the coordinates must be in pixels. The box that the <i>pSrcBox</i> parameter points to must not extend over the edges of the source subresource region or the destination subresource. The source and the destination resource must not be currently mapped. In addition, the resource creation flags restrict whether the resource can participate in the copy operation. 

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>ResourceCopyRegion</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

<div class="alert"><b>Note</b>  The following sections apply only to Microsoft Direct3D version 10.1 and later (that is, Windows Vista with Service Pack 1 (SP1) and later, and Windows Server 2008 and later).
</div>
<div> </div>
The driver can implement a <i>ResourceCopyRegion</i> function that can contain a <b>switch</b> statement to process copying and conversion. That is, the driver can implement one <i>ResourceCopyRegion</i> and can set the <b>pfnResourceConvertRegion</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_1ddi_devicefuncs">D3D10_1DDI_DEVICEFUNCS</a> structure to point to <i>ResourceCopyRegion</i> along with the <b>pfnResourceCopyRegion</b> member of D3D10_1DDI_DEVICEFUNCS. However, to improve performance, the driver can implement separate <i>ResourceCopyRegion</i> and <i>ResourceConvertRegion</i> functions.

The Direct3D 10.1 version  of <i>ResourceCopyRegion</i> has a major functionality difference from the Direct3D 10.0 version in regard to the <b>ResourceDimension</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource">D3D10DDIARG_CREATERESOURCE</a> for the source and destination resources that were created in calls to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource">CreateResource(D3D10)</a> function. For the Direct3D 10.0 version  of <i>ResourceCopyRegion</i>, the <b>ResourceDimension</b> member of D3D10DDIARG_CREATERESOURCE for the source and destination resources must match. The Direct3D 10.1 version of <i>ResourceCopyRegion</i> allows a slight relaxation for the <b>ResourceDimension</b> member of D3D10DDIARG_CREATERESOURCE for the source and destination resources. The Direct3D 10.1 version of <i>ResourceCopyRegion</i> allows for the copying of Tex2D source resources on TexCube destination resources or TexCube source resources on Tex2D destination resources. In addition, the distinction between TexCube at the resource level is gone in Direct3D version 10.1. The Direct3D 10.1 version of <i>ResourceCopyRegion</i> only represents whether it can copy a TexCube. In Direct3D version 10.0, copying a resource, validation of a multiple render target, and so on (that is, various operations that required the resource type to be identical) all included the distinction of TexCube to factor into the resource type. In Direct3D version 10.1, the runtime can determine only Tex2D.

The following sections list conditions for copying and converting:

<b>Copying</b>

For copying, <i>ResourceCopyRegion</i> ensures that the source and destination resources were created through the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource">CreateResource(D3D10)</a> function with the following conditions: 

<ul>
<li>
The destination resource was not created with the D3D10_DDI_USAGE_IMMUTABLE value set in the <b>Usage</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource">D3D10DDIARG_CREATERESOURCE</a> structure. 

</li>
<li>
If either the source or destination resource has the D3D10_DDI_BIND_DEPTH_STENCIL bit set in the <b>BindFlags</b> member of the D3D10DDIARG_CREATERESOURCE or is a multi-sampled resource, <i>ResourceCopyRegion</i> verifies that the <i>pSrcBox</i> parameter is <b>NULL</b>, while the <i>DstX</i>, <i>DstY</i>, and <i>DstZ</i> parameters are 0.

</li>
<li>
The subresource indices are in range.

</li>
<li>
Alignment restrictions apply to coordinates.

</li>
<li>
The source and destination resources are not part of the exact same subresource. 

</li>
<li>
Each source and destination resource format that is specified in the <b>Format</b> member of D3D10DDIARG_CREATERESOURCE is in the same typeless group. 

</li>
<li>
The source and destination resources must have the same number of samples and quality levels; except for single-sampled resources, which must only have the same number of samples. 

</li>
</ul>
<i>ResourceCopyRegion</i> does not ensure that the source box that is offset by the destination offsets fits entirely on the resource. <i>ResourceCopyRegion</i> also does not ensure that no subresources are currently mapped. 

<b>Converting</b>

For conversion, <i>ResourceCopyRegion</i> ensures that the source and destination resources were created through the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource">CreateResource(D3D10)</a> function with the following conditions:

<ul>
<li>
The destination resource was not created with the D3D10_DDI_USAGE_IMMUTABLE value set in the <b>Usage</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource">D3D10DDIARG_CREATERESOURCE</a> structure. 

</li>
<li>
If either the source or destination resource has the D3D10_DDI_BIND_DEPTH_STENCIL bit set in the <b>BindFlags</b> member of the D3D10DDIARG_CREATERESOURCE or is a multi-sampled resource, <i>ResourceCopyRegion</i> verifies that the <i>pSrcBox</i> parameter is <b>NULL</b>, while the <i>DstX</i>, <i>DstY</i>, and <i>DstZ</i> parameters are 0.

</li>
<li>
The subresource indices are in range.

</li>
<li>
Alignment restrictions apply to coordinates.

</li>
<li>
The source and destination resources are not part of the exact same subresource. 

</li>
<li>
Each source and destination resource format that is specified in the <b>Format</b> member of D3D10DDIARG_CREATERESOURCE is in the same typeless group. 

</li>
<li>
Each source and destination resource format that is specified in the <b>Format</b> member of D3D10DDIARG_CREATERESOURCE supports the appropriate conversion operation. 

</li>
<li>
The source and destination resources must have the same number of samples and quality levels; except for single-sampled resources, which must only have the same number of samples. 

</li>
</ul>
<i>ResourceCopyRegion</i> does not ensure that no subresources are currently mapped. <i>ResourceCopyRegion</i> also does not ensure that the source box that is offset by the destination offsets fits entirely on the resource.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_ddi_box">D3D10_DDI_BOX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

