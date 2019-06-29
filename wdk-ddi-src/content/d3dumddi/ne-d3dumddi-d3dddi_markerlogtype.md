---
UID: NE:d3dumddi.D3DDDI_MARKERLOGTYPE
title: D3DDDI_MARKERLOGTYPE (d3dumddi.h)
description: Indicates the type of marker in the Event Tracing for Windows (ETW) log that the user-mode display driver supports.
old-location: display\d3dddi_markerlogtype.htm
tech.root: display
ms.assetid: CBD48828-7DAA-470F-AB9E-34957C579EB5
ms.date: 05/10/2018
ms.keywords: D3DDDIMLT_FT_PROFILE, D3DDDIMLT_NONE, D3DDDIMLT_PROFILE, D3DDDI_MARKERLOGTYPE, D3DDDI_MARKERLOGTYPE enumeration [Display Devices], d3dumddi/D3DDDIMLT_FT_PROFILE, d3dumddi/D3DDDIMLT_NONE, d3dumddi/D3DDDIMLT_PROFILE, d3dumddi/D3DDDI_MARKERLOGTYPE, display.d3dddi_markerlogtype
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
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
- D3dumddi.h
api_name:
- D3DDDI_MARKERLOGTYPE
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_MARKERLOGTYPE
---

# D3DDDI_MARKERLOGTYPE enumeration


## -description


Indicates the type of marker in the Event Tracing for Windows (ETW) log that the user-mode display driver supports.


## -enum-fields




### -field D3DDDIMLT_NONE

No marker type is supported. In this case, the marker type of submitted commands must be <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ne-d3dumddi-d3dddi_markertype">D3DDDI_MARKERTYPE</a>.<b>D3DDDIMT_NONE</b>.


### -field D3DDDIMLT_PROFILE

The context submits GPU work for single-threaded user-mode DDIs. In this case, each time stamp denotes the end of GPU work.


### -field D3DDDIMLT_FT_PROFILE

The context submits GPU work for free-threaded user-mode DDIs. In this case, the driver must have set the <b>Caps</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddi_threading_caps">D3D11DDI_THREADING_CAPS</a> structure to <b>D3D11DDICAPS_FREETHREADED</b>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddi_threading_caps">D3D11DDI_THREADING_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ne-d3dumddi-d3dddi_markertype">D3DDDI_MARKERTYPE</a>
 

 

