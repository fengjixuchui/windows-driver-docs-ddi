---
UID: NS:d3dumddi.D3DDDIARG_PRESENTMULTIPLANEOVERLAY
title: D3DDDIARG_PRESENTMULTIPLANEOVERLAY (d3dumddi.h)
description: Specifies a multiplane overlay resource to display.
old-location: display\d3dddiarg_presentmultiplaneoverlay.htm
tech.root: display
ms.assetid: 862441ee-8a6e-4ddc-8dba-d3d990f45cfc
ms.date: 05/10/2018
keywords: ["D3DDDIARG_PRESENTMULTIPLANEOVERLAY structure"]
ms.keywords: D3DDDIARG_PRESENTMULTIPLANEOVERLAY, D3DDDIARG_PRESENTMULTIPLANEOVERLAY structure [Display Devices], d3dumddi/D3DDDIARG_PRESENTMULTIPLANEOVERLAY, display.d3dddiarg_presentmultiplaneoverlay
f1_keywords:
 - "d3dumddi/D3DDDIARG_PRESENTMULTIPLANEOVERLAY"
 - "D3DDDIARG_PRESENTMULTIPLANEOVERLAY"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
- D3DDDIARG_PRESENTMULTIPLANEOVERLAY
targetos: Windows
req.typenames: D3DDDIARG_PRESENTMULTIPLANEOVERLAY
---

# D3DDDIARG_PRESENTMULTIPLANEOVERLAY structure


## -description


Specifies a multiplane overlay resource to display.


## -struct-fields




### -field VidPnSourceId

[in] The zero-based video present network (VidPN) source identification number of the input that is to be displayed.


### -field Flags

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_presentflags">D3DDDI_PRESENTFLAGS</a> structure that identifies, in bit-field flags, how to display.


### -field FlipInterval

[in] A value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-d3dddi_flipinterval_type">D3DDDI_FLIPINTERVAL_TYPE</a> that indicates the flip interval (that is, if the flip occurs after zero, one, two, three, or four vertical syncs). 


### -field PresentPlaneCount

[in] The number of overlay planes that are available to display.


### -field pPresentPlanes

[in] A pointer to a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_present_multiplane_overlay">D3DDDI_PRESENT_MULTIPLANE_OVERLAY</a> that  describes the overlay plane to display.


### -field Reserved

[in] Reserved for system use. The driver should ignore this member.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-d3dddi_flipinterval_type">D3DDDI_FLIPINTERVAL_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_presentflags">D3DDDI_PRESENTFLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_present_multiplane_overlay">D3DDDI_PRESENT_MULTIPLANE_OVERLAY</a>
 

 

