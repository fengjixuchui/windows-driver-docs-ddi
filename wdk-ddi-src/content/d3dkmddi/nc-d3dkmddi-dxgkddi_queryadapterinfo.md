---
UID: NC:d3dkmddi.DXGKDDI_QUERYADAPTERINFO
title: DXGKDDI_QUERYADAPTERINFO (d3dkmddi.h)
description: The DxgkDdiQueryAdapterInfo function retrieves configuration information from the graphics adapter.
old-location: display\dxgkddiqueryadapterinfo.htm
ms.assetid: f2f4c54c-7413-48e5-a165-d71f35642b6c
ms.date: 05/10/2018
keywords: ["DXGKDDI_QUERYADAPTERINFO callback function"]
ms.keywords: DXGKDDI_QUERYADAPTERINFO, DXGKDDI_QUERYADAPTERINFO callback, DmFunctions_700dcca1-79a6-4d31-953c-00e33c8a404d.xml, DxgkDdiQueryAdapterInfo, DxgkDdiQueryAdapterInfo callback function [Display Devices], d3dkmddi/DxgkDdiQueryAdapterInfo, display.dxgkddiqueryadapterinfo
req.header: d3dkmddi.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
ms.custom: 19H1
f1_keywords:
 - "d3dkmddi/DxgkDdiQueryAdapterInfo"
 - "DxgkDdiQueryAdapterInfo"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkDdiQueryAdapterInfo
product:
 - Windows
dev_langs:
 - c++
---

# DXGKDDI_QUERYADAPTERINFO callback function

## -description

The <i>DxgkDdiQueryAdapterInfo</i> function retrieves configuration information from the graphics adapter.

## -parameters

### -param hAdapter

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.

### -param pQueryAdapterInfo

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a> structure that the display miniport driver fills with the configuration information for the graphics adapter.

## -returns

<i>DxgkDdiQueryAdapterInfo</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|DxgkDdiQueryAdapterInfo successfully retrieved the configuration information.|
|STATUS_INVALID_PARAMETER|Parameters that were passed to DxgkDdiQueryAdapterInfo contained errors that prevented it from completing.|
|STATUS_NO_MEMORY|DxgkDdiQueryAdapterInfo could not allocate memory that was required for it to complete.|
|STATUS_GRAPHICS_DRIVER_MISMATCH|The display miniport driver is not compatible with the user-mode display driver that initiated the call to DxgkDdiQueryAdapterInfo (that is, supplied private data for a query to the display miniport driver).|

## -remarks

When the user-mode display driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryadapterinfocb">pfnQueryAdapterInfoCb</a> function, a call to the <i>DxgkDdiQueryAdapterInfo</i> function is initiated. <i>DxgkDdiQueryAdapterInfo</i> receives the DXGKQAITYPE_UMDRIVERPRIVATE value in the <b>Type</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a> structure that the <i>pQueryAdapterInfo</i> parameter points to. This function also receives a proprietary buffer in the <b>pOutputData</b> member that it fills with the configuration information that is necessary for the user-mode display driver to identify the adapter. 

If the DirectX graphics kernel subsystem (which is part of <i>Dxgkrnl.sys</i>) specifies the DXGKQAITYPE_DRIVERCAPS value in the <b>Type</b> member of DXGKARG_QUERYADAPTERINFO when the subsystem calls <i>DxgkDdiQueryAdapterInfo</i>, the display miniport driver should populate the provided <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a> structure with information that the subsystem can use.

If the DirectX graphics kernel subsystem supplies the DXGKQAITYPE_QUERYSEGMENT value in the <b>Type</b> member of DXGKARG_QUERYADAPTERINFO, the display miniport driver should provide information about the memory segments that it supports. For more information about memory segments, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/initializing-use-of-memory-segments">Initializing Use of Memory Segments</a>. 

<i>DxgkDdiQueryAdapterInfo</i> should be made pageable. 

> [!NOTE]
> All drivers that support WDDM 2.6 must implement the DxgkDdiQueryAdapterInfo callback.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryadapterinfocb">pfnQueryAdapterInfoCb</a>

