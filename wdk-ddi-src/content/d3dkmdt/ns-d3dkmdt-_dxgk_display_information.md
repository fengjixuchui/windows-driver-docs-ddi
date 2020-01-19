---
UID: NS:d3dkmdt._DXGK_DISPLAY_INFORMATION
title: _DXGK_DISPLAY_INFORMATION (d3dkmdt.h)
description: Contains the display information that is passed between the operating system and the display miniport driver when the driver is started or stopped in response to a Plug and Play (PnP) event.
old-location: display\dxgk_display_information.htm
tech.root: display
ms.assetid: e6902724-a81b-4a06-8089-a8e98392dc78
ms.date: 05/10/2018
ms.keywords: "*PDXGK_DISPLAY_INFORMATION, DXGK_DISPLAY_INFORMATION, DXGK_DISPLAY_INFORMATION structure [Display Devices], PDXGK_DISPLAY_INFORMATION, PDXGK_DISPLAY_INFORMATION structure pointer [Display Devices], _DXGK_DISPLAY_INFORMATION, d3dkmdt/DXGK_DISPLAY_INFORMATION, d3dkmdt/PDXGK_DISPLAY_INFORMATION, display.dxgk_display_information"
ms.topic: struct
f1_keywords:
 - "d3dkmdt/DXGK_DISPLAY_INFORMATION"
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
- D3dkmdt.h
api_name:
- DXGK_DISPLAY_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: DXGK_DISPLAY_INFORMATION, *PDXGK_DISPLAY_INFORMATION
---

# _DXGK_DISPLAY_INFORMATION structure


## -description


Contains the display information that is passed between the operating system and the display miniport driver when the driver is started or stopped in response to a Plug and Play (PnP) event.


## -struct-fields




### -field Width

A UINT value that specifies the width of the current display mode in units of pixels.


### -field Height

A UINT value that specifies the height of the current display mode  in units of pixels.


### -field Pitch

A UINT value that specifies the total number of bytes contained in one screen line.


### -field ColorFormat

A value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a> that indicates the pixel color format of the current display mode. The driver does not have to support all color formats in the <b>D3DDDIFORMAT</b> structure. For more information on formats that must be supported, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_acquire_post_display_ownership">DxgkCbAcquirePostDisplayOwnership</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_stop_device_and_release_post_display_ownership">DxgkDdiStopDeviceAndReleasePostDisplayOwnership</a>.


### -field PhysicAddress

The physical start address of the frame buffer for the current display mode.


### -field TargetId

An integer value that specifies the identifier of the video present target on the display adapter that the display device is connected to.


### -field AcpiId

A ULONG value that specifies the ACPI identifier of the video present target specified by the <b>TargetId</b> member.

<div class="alert"><b>Note</b>  If the video present target is not an ACPI device, this member must be set to zero.</div>
<div> </div>

## -remarks



For more information on the use of the members of <b>DXGK_DISPLAY_INFORMATION</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_acquire_post_display_ownership">DxgkCbAcquirePostDisplayOwnership</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_stop_device_and_release_post_display_ownership">DxgkDdiStopDeviceAndReleasePostDisplayOwnership</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_acquire_post_display_ownership">DxgkCbAcquirePostDisplayOwnership</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_stop_device_and_release_post_display_ownership">DxgkDdiStopDeviceAndReleasePostDisplayOwnership</a>
 

 

