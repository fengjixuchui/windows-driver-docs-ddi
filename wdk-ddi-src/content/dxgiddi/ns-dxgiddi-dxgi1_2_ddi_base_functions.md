---
UID: NS:dxgiddi.DXGI1_2_DDI_BASE_FUNCTIONS
title: DXGI1_2_DDI_BASE_FUNCTIONS (dxgiddi.h)
description: Contains pointers to functions that a Windows Display Driver Model (WDDM) 1.2 and later user-mode display driver can implement to perform low-level tasks like presenting rendered frames to an output, controlling gamma, getting notifications regarding shared and Windows Graphics Device Interface (GDI) interoperable surfaces, and managing a full-screen transition.
old-location: display\dxgi1_2_ddi_base_functions.htm
tech.root: display
ms.assetid: 7A1CD16A-4B7A-40FE-8650-AAD8CAC10FB0
ms.date: 05/10/2018
keywords: ["DXGI1_2_DDI_BASE_FUNCTIONS structure"]
ms.keywords: DXGI1_2_DDI_BASE_FUNCTIONS, DXGI1_2_DDI_BASE_FUNCTIONS structure [Display Devices], display.dxgi1_2_ddi_base_functions, dxgiddi/DXGI1_2_DDI_BASE_FUNCTIONS
f1_keywords:
 - "dxgiddi/DXGI1_2_DDI_BASE_FUNCTIONS"
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8,WDDM 1.2 and later
req.target-min-winversvr: Windows Server 2012
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
- Dxgiddi.h
api_name:
- DXGI1_2_DDI_BASE_FUNCTIONS
product:
- Windows
targetos: Windows
req.typenames: DXGI1_2_DDI_BASE_FUNCTIONS
---

# DXGI1_2_DDI_BASE_FUNCTIONS structure


## -description


Contains pointers to functions that a Windows Display Driver Model (WDDM) 1.2 and later user-mode display driver can implement to perform low-level tasks like presenting rendered frames to an output, controlling gamma, getting notifications regarding shared and Windows Graphics Device Interface (GDI) interoperable surfaces, and managing a full-screen transition.


## -struct-fields




### -field pfnPresent

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">PresentDXGI</a> function.


### -field pfnGetGammaCaps

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">GetGammaCapsDXGI</a> function.


### -field pfnSetDisplayMode

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_1_ddi_base_functions">SetDisplayModeDXGI</a> function.


### -field pfnSetResourcePriority

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">SetResourcePriorityDXGI</a> function.


### -field pfnQueryResourceResidency

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">QueryResourceResidencyDXGI</a> function.


### -field pfnRotateResourceIdentities

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">RotateResourceIdentitiesDXGI</a> function.


### -field pfnBlt

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">BltDXGI</a> function.

The Direct3D runtime might set the <b>Flags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_blt1">DXGI_DDI_ARG_BLT1</a> structure that the <i>pBltData</i> parameter points to in such a way as to require the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_2_ddi_base_functions">Blt1DXGI</a> function to perform a <a href="https://docs.microsoft.com/windows-hardware/drivers/">bit-block transfer (bitblt)</a> operation that resolves multi-sampled resources, performs color-format conversion, and performs a stretch or shrink all at once. However, the Direct3D runtime will never set the <b>Flags</b> member of <b>DXGI_DDI_ARG_BLT1</b> to zero (that is, no flags set) together with the <b>DXGI_DDI_MODE_ROTATION_IDENTITY</b> value set in the <b>Rotate</b> member of <b>DXGI_DDI_ARG_BLT1</b> (that is, to indicate no rotation) to perform a straight memory copy operation. Instead, unless both resources are multi-sampled, the Direct3D runtime calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcecopy">ResourceCopy</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_resourcecopyregion">ResourceCopyRegion(D3D11_1)</a> function to perform a straight memory copy operation.

The quality of the stretch or shrink that the user-mode display driver performs must be as good as the stretch or shrink that a bilinear filter performs.

The Direct3D runtime will call the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_2_ddi_base_functions">Blt1DXGI</a> function infrequently. That is, the runtime should call <i>Blt1DXGI</i> no more than once or twice per frame because the runtime uses <i>Blt1DXGI</i> primarily to support a presentation.

 When the runtime calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_2_ddi_base_functions">Blt1DXGI</a> for a presentation, the runtime sets the <b>Present</b> bit-field flag in the <b>Flags</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_blt1">DXGI_DDI_ARG_BLT1</a>. The runtime sets the <b>Present</b> bit-field flag to inform the driver that there are extra requirements for the bitblt and that extra synchronization may be necessary (for example, the runtime might need to perform extra synchronization in computer configurations that contain two graphics adapters that each handle separate parts of the display). When the <b>Present</b> bit-field flag is set, the driver should perform a copy operation from an application's back buffers to the shared surface of the DWM. Because synchronization for this type of copy operation is inexact, tearing artifacts should be the worst type of artifacts that a user experiences. For this type of copy operation, the driver should not use a multi-pass approach by first resolving into the destination surface and then color converting the results in-place because the possible artifacts would be much worse.

If the driver supports returning <b>DXGI_DDI_ERR_UNSUPPORTED</b> during the creation of a primary surface (that is, returning <b>DXGI_DDI_ERR_UNSUPPORTED</b> from a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource">CreateResource(D3D10)</a> function with the <b>D3D10_DDI_BIND_PRESENT</b> flag set in the <b>BindFlags</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource">D3D10DDIARG_CREATERESOURCE</a> along with the <b>pPrimaryDesc</b> member of <b>D3D10DDIARG_CREATERESOURCE</b> set to non-<b>NULL</b>), the driver must also support rotation during a copy operation. If the driver never returns <b>DXGI_DDI_ERR_UNSUPPORTED</b> from a call to its <i>CreateResource(D3D10)</i> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createresource">CreateResource(D3D11)</a> function, the runtime will never pass the <b>DXGI_DDI_MODE_ROTATION_ROTATE90</b>, <b>DXGI_DDI_MODE_ROTATION_ROTATE180</b>, or <b>DXGI_DDI_MODE_ROTATION_ROTATE270</b> value to the <b>Rotate</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_blt1">DXGI_DDI_ARG_BLT1</a>. Therefore, in this situation, the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_2_ddi_base_functions">Blt1DXGI</a> function is not required to support rotation.

The runtime sets a value in the <b>Rotate</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_blt1">DXGI_DDI_ARG_BLT1</a> to indicate the number of degrees to rotate counter-clockwise the contents of the source before the driver copies the contents to the destination. Rotation is specified in increments of 90 degrees.

<div class="alert"><b>Note</b>    When the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_2_ddi_base_functions">Blt1DXGI</a> function copies sRGB-formatted content from a source surface to a non-sRGB destination surface, the driver should copy the sRGB content unchanged (that is, the driver should not perform the sRGB to linear conversion).</div>
<div> </div>
<b>Source restrictions</b>

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_2_ddi_base_functions">Blt1DXGI</a> function always uses a whole source subresource (versus some sub-rectangular area) to perform the bitblt operation. In addition, the source is a <b>D3D10DDIRESOURCE_TEXTURE2D</b> representation (specified in the <b>ResourceDimension</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource">D3D10DDIARG_CREATERESOURCE</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createresource">D3D11DDIARG_CREATERESOURCE</a> when the source is created in a call to the user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource">CreateResource(D3D10)</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createresource">CreateResource(D3D11)</a> function, respectively). When the runtime sets the <b>Resolve</b> bitfield in the <b>Flags</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_blt1">DXGI_DDI_ARG_BLT1</a>, the source is a multi-sampled resource. The source resource is restricted to a resource in which the <b>D3D10_DDI_BIND_PRESENT</b> flag was set in the <b>BindFlags</b> member of <b>D3D10DDIARG_CREATERESOURCE</b> or <b>D3D11DDIARG_CREATERESOURCE</b>. The format of the source (specified in the <b>Format</b> member of <b>D3D10DDIARG_CREATERESOURCE</b> or <b>D3D11DDIARG_CREATERESOURCE</b>) is restricted to display mode formats, specified by the following values from the <a href="https://msdn.microsoft.com/dce61bc4-4ed5-4e64-84e8-6db88025e5c2">DXGI_FORMAT</a> enumeration: 

<ul>
<li>
<b>DXGI_FORMAT_B5G6R5_UNORM</b>

</li>
<li>
<b>DXGI_FORMAT_B5G5R5A1_UNORM</b>

</li>
<li>
<b>DXGI_FORMAT_B8G8R8A8_UNORM</b> (See Note below.)

</li>
<li>
<b>DXGI_FORMAT_B8G8R8X8_UNORM</b>

</li>
<li>
<b>DXGI_FORMAT_R16G16B16A16_FLOAT</b>

</li>
<li>
<b>DXGI_FORMAT_R10G10B10A2_UNORM</b>

</li>
<li>
<b>DXGI_FORMAT_R8G8B8A8_UNORM</b>

</li>
<li>
<b>DXGI_FORMAT_R8G8B8A8_UNORM_SRGB</b>

</li>
</ul>
<div class="alert"><b>Note</b>  If the driver supports the source format <b>DXGI_FORMAT_B8G8R8A8_UNORM</b>, these restrictions apply:<ul>
<li>When the driver performs a bitblt operation from a floating-point format to an integer format such as BGRA8888, it must implicitly encode gamma into the results.</li>
<li>Conversely, when the driver performs a bitblt operation from an integer format to a floating-point format, it must implicitly remove gamma encoding from the results.</li>
</ul>
</div>
<div> </div>
<b>Destination restrictions</b>

The destination is also a <b>D3D10DDIRESOURCE_TEXTURE2D</b> representation. The format of the destination is also restricted to display mode formats. The destination resource is restricted to a resource that is bound as a render target (<b>D3D10_DDI_BIND_RENDER_TARGET</b> set in the <b>BindFlags</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource">D3D10DDIARG_CREATERESOURCE</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createresource">D3D11DDIARG_CREATERESOURCE</a>).

<b>Creating a stereo back buffer</b>

Beginning in Windows 8, if the driver must create a stereo back buffer, it should set members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource">D3D10DDIARG_CREATERESOURCE</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createresource">D3D11DDIARG_CREATERESOURCE</a> structure, respectively, pointed to by the <i>pCreateResource</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource">CreateResource(D3D10)</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createresource">CreateResource(D3D11)</a> functions, as follows:

<ol>
<li>Set the <b>ArraySize</b> member to a value of 2.</li>
<li>Set the <b>D3D10_DDI_BIND_PRESENT</b> flag value in the <b>BindFlags</b> member.</li>
</ol>
Additionally, to support stereo presentation, the BltDXGI function must allow any values for the <b>DstSubresource</b> and <b>SrcSubresource</b> members of  the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_blt">DXGI_DDI_ARG_BLT</a> structure that are within the range of the source and destination resources.



### -field pfnResolveSharedResource

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_1_ddi_base_functions">ResolveSharedResourceDXGI</a> function.


### -field pfnBlt1

A pointer to the driver's  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_2_ddi_base_functions">Blt1DXGI</a> function.


### -field pfnOfferResources

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_offerresources">pfnOfferResources</a> function.


### -field pfnReclaimResources

Called by the DXGI runtime to reclaim video memory resources that the user-mode display driver  previously offered  for reuse. Implemented by WDDM 1.2 and later user-mode display drivers.




### -field pfnGetMultiplaneOverlayCaps

Called by the Microsoft DirectX Graphics Infrastructure (DXGI) runtime to request that the user-mode display driver get basic overlay plane capabilities. Optionally implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.

**Syntax**

```cpp
pfnGetMultiPlaneOverlayCaps GetMultiPlaneOverlayCaps;

HRESULT __stdcall* GetMultiPlaneOverlayCaps(
    DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS *pCaps
)
{ ... }
```

**Parameters*

*pCaps* 
A pointer to a [DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS](ns-dxgiddi-_dxgi_ddi_arg_getmultiplaneoverlaycaps.md) structure that specifies the overlay plane capabilities.

**Return value**

Returns one of the following values.

* **S_OK**  The driver successfully provided the overlay plane capabilities.
* **D3DDDIERR_DEVICEREMOVED**  The driver detected that the display adapter was removed, so the driver did not complete the operation. If the driver is not aware of the adapter removal, the driver is not required to return this error code.


### -field pfnGetMultiplaneOverlayFilterRange

This member is reserved and should be set to zero. Supported starting with Windows 8.1.


### -field pfnCheckMultiplaneOverlaySupport

Called by the Microsoft DirectX Graphics Infrastructure (DXGI) runtime to check the details on hardware support for multiplane overlays.

**Syntax**

```cpp
PFND3DDDI_CHECKMULTIPLANEOVERLAYSUPPORT pfnCheckMultiplaneOverlaySupport;

HRESULT __stdcall* pfnCheckMultiplaneOverlaySupport(
   DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY *pSupport
)
{ ... }
```

**Parameter**

*pSupport* A pointer to a DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT structure that describes how to display to the destination surface. 

**Return value**

If this callback function succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

### -field pfnPresentMultiplaneOverlay

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/nc-dxgiddi-pfnddxgiddi_present_multiplane_overlaycb">pfnPresentMultiplaneOverlay (DXGI)</a> function. Supported starting with Windows 8.1.

#### - pfnCheckMultiPlaneOverlaySupport

Called by the DXGI runtime to check the details on hardware support for multiplane overlays.



#### pSupport

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-_dxgi_ddi_arg_checkmultiplaneoverlaysupport">DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT</a> structure that describes how to display to the destination surface. 






## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_3_ddi_base_functions">DXGI1_3_DDI_BASE_FUNCTIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_args">DXGI_DDI_BASE_ARGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">DXGI_DDI_BASE_FUNCTIONS</a>
 

 

