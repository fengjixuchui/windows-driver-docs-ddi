---
UID: NS:d3dkmddi._DXGK_VIDPNSOURCEMODESET_INTERFACE
title: _DXGK_VIDPNSOURCEMODESET_INTERFACE (d3dkmddi.h)
description: The DXGK_VIDPNSOURCEMODESET_INTERFACE structure contains pointers to functions that belong to the VidPn Source Mode Set interface, which is implemented by the video present network (VidPN) manager.
old-location: display\dxgk_vidpnsourcemodeset_interface.htm
ms.assetid: c608643f-e791-44b8-8719-4e98e10fa7b0
ms.date: 10/30/2018
keywords: ["DXGK_VIDPNSOURCEMODESET_INTERFACE structure"]
ms.keywords: DXGK_VIDPNSOURCEMODESET_INTERFACE, DXGK_VIDPNSOURCEMODESET_INTERFACE structure [Display Devices], DmStructs_8e8b4b99-8121-4cff-9d1b-f88a9041e7cd.xml, _DXGK_VIDPNSOURCEMODESET_INTERFACE, d3dkmddi/DXGK_VIDPNSOURCEMODESET_INTERFACE, display.dxgk_vidpnsourcemodeset_interface
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
req.typenames: DXGK_VIDPNSOURCEMODESET_INTERFACE
f1_keywords:
 - _DXGK_VIDPNSOURCEMODESET_INTERFACE
 - d3dkmddi/_DXGK_VIDPNSOURCEMODESET_INTERFACE
 - DXGK_VIDPNSOURCEMODESET_INTERFACE
 - d3dkmddi/DXGK_VIDPNSOURCEMODESET_INTERFACE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGK_VIDPNSOURCEMODESET_INTERFACE
---

# _DXGK_VIDPNSOURCEMODESET_INTERFACE structure


## -description

The DXGK_VIDPNSOURCEMODESET_INTERFACE structure contains pointers to functions that belong to the VidPn Source mode set interface in [VidPN Objects and Interfaces](https://docs.microsoft.com/windows-hardware/drivers/display/vidpn-objects-and-interfaces), which is implemented by the video present network (VidPN) manager.

## -struct-fields

### -field pfnGetNumModes

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_getnummodes">pfnGetNumModes</a> function.

### -field pfnAcquireFirstModeInfo

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirefirstmodeinfo">pfnAcquireFirstModeInfo</a> function.

### -field pfnAcquireNextModeInfo

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirenextmodeinfo">pfnAcquireNextModeInfo</a> function.

### -field pfnAcquirePinnedModeInfo

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_acquirepinnedmodeinfo">pfnAcquirePinnedModeInfo</a> function.

### -field pfnReleaseModeInfo

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_releasemodeinfo">pfnReleaseModeInfo</a> function.

### -field pfnCreateNewModeInfo

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_createnewmodeinfo">pfnCreateNewModeInfo</a> function.

### -field pfnAddMode

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_addmode">pfnAddMode</a> function.

### -field pfnPinMode

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_pinmode">pfnPinMode</a> function.

## -remarks

The display miniport driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_acquiresourcemodeset">pfnAcquireSourceModeSet</a> function of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">VidPn interface</a> to obtain a handle to a VidPN source mode set object and a pointer to a DXGK_VIDPNSOURCEMODESET_INTERFACE structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the VidPN source mode set object.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_source_mode">D3DKMDT_VIDPN_SOURCE_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_monitorsourcemodeset_interface">DXGK_MONITORSOURCEMODESET_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_vidpntargetmodeset_interface">DXGK_VIDPNTARGETMODESET_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_acquiresourcemodeset">pfnAcquireSourceModeSet</a>

