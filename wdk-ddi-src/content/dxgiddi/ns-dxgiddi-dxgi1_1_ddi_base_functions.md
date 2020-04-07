---
UID: NS:dxgiddi.DXGI1_1_DDI_BASE_FUNCTIONS
title: DXGI1_1_DDI_BASE_FUNCTIONS (dxgiddi.h)
description: The DXGI1_1_DDI_BASE_FUNCTIONS structure contains pointers to functions that the user-mode display driver can implement to perform low-level tasks like presenting rendered frames to an output, controlling gamma, getting notifications regarding shared and GDI interoperable surfaces, and managing a full-screen transition.
old-location: display\dxgi1_1_ddi_base_functions.htm
tech.root: display
ms.assetid: 624da381-86c9-46d8-82eb-1f21e752ea57
ms.date: 05/10/2018
keywords: ["DXGI1_1_DDI_BASE_FUNCTIONS structure"]
ms.keywords: DXGI1_1_DDI_BASE_FUNCTIONS, DXGI1_1_DDI_BASE_FUNCTIONS structure [Display Devices], UMDisplayDriver_Dx10param_Structs_92bae538-7b48-48d5-a26f-c593ff5875cf.xml, display.dxgi1_1_ddi_base_functions, dxgiddi/DXGI1_1_DDI_BASE_FUNCTIONS
f1_keywords:
 - "dxgiddi/DXGI1_1_DDI_BASE_FUNCTIONS"
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: DXGI1_1_DDI_BASE_FUNCTIONS is supported beginning with the Windows 7 operating system.
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
- dxgiddi.h
api_name:
- DXGI1_1_DDI_BASE_FUNCTIONS
product:
- Windows
targetos: Windows
req.typenames: DXGI1_1_DDI_BASE_FUNCTIONS
---

# DXGI1_1_DDI_BASE_FUNCTIONS structure


## -description


The DXGI1_1_DDI_BASE_FUNCTIONS structure contains pointers to functions that the user-mode display driver can implement to perform low-level tasks like presenting rendered frames to an output, controlling gamma, getting notifications regarding shared and GDI interoperable surfaces, and managing a full-screen transition. 


## -struct-fields




### -field pfnPresent

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">PresentDXGI</a> function.


### -field pfnGetGammaCaps

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">GetGammaCapsDXGI</a> function.


### -field pfnSetDisplayMode

The <i>SetDisplayModeDXGI</i> function switches to a display mode or primary that the GDI desktop does not support.

The Microsoft Direct3D runtime calls <i>SetDisplayModeDXGI</i> to switch to a display mode or primary that the GDI desktop does not support. The following list describes examples of such primaries: 

<ul>
<li>
Primaries that are created with 10-bits-per-channel (10:10:10:2) display and render target formats (for example, D3DFMT_A2R10G10B10)

</li>
<li>
Multiple-sampled primaries where the multiple-sampling is performed while scanning-out 

</li>
<li>
Persistent primaries that full-screen Microsoft DirectX version 10 applications use 

</li>
</ul>
The Direct3D runtime calls the user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource">CreateResource(D3D10)</a> function to create the primary to be scanned out. However, the driver should program the hardware to scan out only when its <i>SetDisplayModeDXGI</i> function is called. Therefore, the runtime sets the <b>hResource</b> and <b>SubResourceIndex</b> members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_setdisplaymode">DXGI_DDI_ARG_SETDISPLAYMODE</a> structure that is pointed to by the <i>pDisplayModeData</i> parameter to the primary that was created through the call to the driver's <i>CreateResourceD3D10</i> function. The driver should then translate the primary that <b>hResource</b> and <b>SubResourceIndex</b> represent to a primary allocation handle. After the driver makes this translation, the driver should pass the resulting handle in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setdisplaymodecb">pfnSetDisplayModeCb</a> function, which then initiates a call to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_commitvidpn">DxgkDdiCommitVidPn</a> function. 

The user-mode display driver can set the <b>hPrimaryAllocation</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_setdisplaymode">D3DDDICB_SETDISPLAYMODE</a> structure in the call to <b>pfnSetDisplayModeCb</b> to scan out any allocation. However, the allocation must be marked as a primary (that is, the user-mode display driver must have set the <b>Primary</b> bit-field flag in the <b>Flags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_allocationinfo">D3DDDI_ALLOCATIONINFO</a> structure in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_allocatecb">pfnAllocateCb</a> function to create the allocation).



#### pDisplayModeData

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_setdisplaymode">DXGI_DDI_ARG_SETDISPLAYMODE</a> structure that specifies parameters for setting the display mode.


### -field pfnSetResourcePriority

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">SetResourcePriorityDXGI</a> function.


### -field pfnQueryResourceResidency

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">QueryResourceResidencyDXGI</a> function.


### -field pfnRotateResourceIdentities

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">RotateResourceIdentitiesDXGI</a> function.


### -field pfnBlt

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">BltDXGI</a> function.


### -field pfnResolveSharedResource

The <i>ResolveSharedResourceDXGI</i> function informs a user-mode display driver that the ownership of a shared surface changed or that a surface is being used for GDI interoperation.

The Direct3D runtime calls <i>ResolveSharedResourceDXGI</i> when an application calls one of the following functions:

<ul>
<li>
<b>IDXGIKeyedMutex::ReleaseSynch</b> on a synchronized shared surface 

</li>
<li>
<b>IDXGISurface1::GetDC</b> for a GDI interoperable surface 

</li>
</ul>
The runtime calls the driver's <i>ResolveSharedResourceDXGI</i> function every time a shared surface owner changes or when a surface is used for GDI interoperation. 

The driver implements <i>ResolveSharedResourceDXGI</i> to appropriately manage resources for multiple GPU scenarios. Each resource might be divided across memory for multiple GPUs to render on. The driver can implement <i>ResolveSharedResourceDXGI</i> to remerge each resource so that the new resource owner has the merged resource. The driver must flush any partially built command buffers that might modify the resource.

Windows 7 provides the IS_DXGI1_1_BASE_FUNCTIONS macro (which is defined in the <i>D3D10umddi.h</i> header file) to allow the user-mode display driver to determine whether it receives a pointer to a <b>DXGI1_1_DDI_BASE_FUNCTIONS</b> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">DXGI_DDI_BASE_FUNCTIONS</a> structure in a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function. The DXGI1_1_DDI_BASE_FUNCTIONS structure includes the <b>pfnResolveSharedResource</b> member that the driver can fill with a pointer to its <i>ResolveSharedResourceDXGI</i> function. If IS_DXGI1_1_BASE_FUNCTIONS returns <b>TRUE</b>, the driver expects to receive a pointer to a DXGI1_1_DDI_BASE_FUNCTIONS structure in the <b>pDXGIDDIBaseFunctions</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_args">DXGI_DDI_BASE_ARGS</a> structure that the <b>DXGIBaseDDI</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a> structure specifies. Otherwise, if IS_DXGI1_1_BASE_FUNCTIONS returns <b>FALSE</b>, the driver expects to receive a pointer to a DXGI_DDI_BASE_FUNCTIONS structure. Windows 7 provides the IS_DXGI1_1_BASE_FUNCTIONS macro to allow newer version drivers to work on older version runtimes. The drivers can then determine whether they will corrupt memory if they attempt to fill the <b>pfnResolveSharedResource</b> member of <b>DXGI1_1_DDI_BASE_FUNCTIONS</b> with a pointer to the <i>ResolveSharedResourceDXGI</i> function.



#### pResourceData

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_arg_resolvesharedresource">DXGI_DDI_ARG_RESOLVESHAREDRESOURCE</a> structure that specifies parameters for the display device and the surface that is associated with the display device. 


## -remarks



Windows 7 provides the IS_DXGI1_1_BASE_FUNCTIONS macro (which is defined in the <i>D3D10umddi.h</i> header file) to allow the user-mode display driver to determine whether it receives a pointer to a DXGI1_1_DDI_BASE_FUNCTIONS or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">DXGI_DDI_BASE_FUNCTIONS</a> structure in a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function. The DXGI1_1_DDI_BASE_FUNCTIONS structure includes the <b>pfnResolveSharedResource</b> member that the driver can fill with a pointer to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_1_ddi_base_functions">ResolveSharedResourceDXGI</a> function. If IS_DXGI1_1_BASE_FUNCTIONS returns <b>TRUE</b>, the driver expects to receive a pointer to a DXGI1_1_DDI_BASE_FUNCTIONS structure in the <b>pDXGIDDIBaseFunctions</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_args">DXGI_DDI_BASE_ARGS</a> structure that the <b>DXGIBaseDDI</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a> structure specifies. Otherwise, if IS_DXGI1_1_BASE_FUNCTIONS returns <b>FALSE</b>, the driver expects to receive a pointer to a DXGI_DDI_BASE_FUNCTIONS structure. Windows 7 provides the IS_DXGI1_1_BASE_FUNCTIONS macro to allow newer version drivers to work on older version runtimes. The drivers can then determine whether they will corrupt memory if they attempt to fill the <b>pfnResolveSharedResource</b> member of <b>DXGI1_1_DDI_BASE_FUNCTIONS</b> with a pointer to a <i>ResolveSharedResourceDXGI</i> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">BltDXGI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_args">DXGI_DDI_BASE_ARGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">DXGI_DDI_BASE_FUNCTIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">GetGammaCapsDXGI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">PresentDXGI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">QueryResourceResidencyDXGI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_resolvesharedresource">ResolveSharedResource</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_1_ddi_base_functions">ResolveSharedResourceDXGI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">RotateResourceIdentitiesDXGI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_1_ddi_base_functions">SetDisplayModeDXGI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">SetResourcePriorityDXGI</a>
 

 

