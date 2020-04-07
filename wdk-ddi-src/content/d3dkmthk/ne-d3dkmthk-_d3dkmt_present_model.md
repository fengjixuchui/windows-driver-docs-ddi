---
UID: NE:d3dkmthk._D3DKMT_PRESENT_MODEL
title: _D3DKMT_PRESENT_MODEL (d3dkmthk.h)
description: The D3DKMT_PRESENT_MODEL enumeration type contains values that indicate the model for a present operation.
old-location: display\d3dkmt_present_model.htm
ms.assetid: 4663cc8e-ce69-4454-afff-03d4a8d82dfb
ms.date: 05/10/2018
keywords: ["_D3DKMT_PRESENT_MODEL enumeration"]
ms.keywords: D3DKMT_PM_REDIRECTED_BLT, D3DKMT_PM_REDIRECTED_COMPOSITION, D3DKMT_PM_REDIRECTED_FLIP, D3DKMT_PM_REDIRECTED_GDI, D3DKMT_PM_REDIRECTED_GDI_SYSMEM, D3DKMT_PM_REDIRECTED_VISTABLT, D3DKMT_PM_SCREENCAPTUREFENCE, D3DKMT_PM_UNINITIALIZED, D3DKMT_PRESENT_MODEL, D3DKMT_PRESENT_MODEL enumeration [Display Devices], OpenGL_Structs_b2e4c00b-9072-449d-84c0-7958200e7d9a.xml, _D3DKMT_PRESENT_MODEL, d3dkmthk/D3DKMT_PM_REDIRECTED_BLT, d3dkmthk/D3DKMT_PM_REDIRECTED_COMPOSITION, d3dkmthk/D3DKMT_PM_REDIRECTED_FLIP, d3dkmthk/D3DKMT_PM_REDIRECTED_GDI, d3dkmthk/D3DKMT_PM_REDIRECTED_GDI_SYSMEM, d3dkmthk/D3DKMT_PM_REDIRECTED_VISTABLT, d3dkmthk/D3DKMT_PM_SCREENCAPTUREFENCE, d3dkmthk/D3DKMT_PM_UNINITIALIZED, d3dkmthk/D3DKMT_PRESENT_MODEL, display.d3dkmt_present_model
f1_keywords:
 - "d3dkmthk/D3DKMT_PRESENT_MODEL"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_PRESENT_MODEL is supported beginning with the Windows 7 operating system.
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
- d3dkmthk.h
api_name:
- D3DKMT_PRESENT_MODEL
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_PRESENT_MODEL
---

# _D3DKMT_PRESENT_MODEL enumeration


## -description


The D3DKMT_PRESENT_MODEL enumeration type contains values that indicate the model for a present operation.


## -syntax


```cpp
typedef enum _D3DKMT_PRESENT_MODEL {
  D3DKMT_PM_UNINITIALIZED           = 0,
  D3DKMT_PM_REDIRECTED_GDI          = 1,
  D3DKMT_PM_REDIRECTED_FLIP         = 2,
  D3DKMT_PM_REDIRECTED_BLT          = 3,
  D3DKMT_PM_REDIRECTED_VISTABLT     = 4,
  D3DKMT_PM_SCREENCAPTUREFENCE      = 5,
  D3DKMT_PM_REDIRECTED_GDI_SYSMEM   = 6,
  D3DKMT_PM_REDIRECTED_COMPOSITION  = 7
} D3DKMT_PRESENT_MODEL;
```


## -enum-fields




### -field D3DKMT_PM_UNINITIALIZED

The present-operation model is not initialized.


### -field D3DKMT_PM_REDIRECTED_GDI

The present-operation model is redirected GDI.


### -field D3DKMT_PM_REDIRECTED_FLIP

The present-operation model is redirected flip.


### -field D3DKMT_PM_REDIRECTED_BLT

The present-operation model is redirected bit-block transfer (bitblt).


### -field D3DKMT_PM_REDIRECTED_VISTABLT

The present-operation model is redirected Windows Vista bitblt.


### -field D3DKMT_PM_SCREENCAPTUREFENCE

The present-operation model is screen capture through a fence.


### -field D3DKMT_PM_REDIRECTED_GDI_SYSMEM

The present-operation model is redirected system GDI.


### -field D3DKMT_PM_REDIRECTED_COMPOSITION

The present-operation model is redirected composition swap chain presentation. This type of presentation is used for XAML-based apps.


### -field D3DKMT_PM_SURFACECOMPLETE


### -field D3DKMT_PM_FLIPMANAGER :


## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_presenthistorytoken.md">D3DKMT_PRESENTHISTORYTOKEN</a>



 

 


