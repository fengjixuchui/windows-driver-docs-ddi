---
UID: NF:d3dkmthk.D3DKMTUpdateOverlay
title: D3DKMTUpdateOverlay function (d3dkmthk.h)
description: The D3DKMTUpdateOverlay function modifies a kernel-mode overlay object.
old-location: display\d3dkmtupdateoverlay.htm
ms.assetid: bd8fc34a-60a3-4ae7-b13e-50d8b4342834
ms.date: 05/10/2018
keywords: ["D3DKMTUpdateOverlay function"]
ms.keywords: D3DKMTUpdateOverlay, D3DKMTUpdateOverlay function [Display Devices], OpenGL_Functions_bddc75da-dc62-43cf-8ee7-ec9958198669.xml, d3dkmthk/D3DKMTUpdateOverlay, display.d3dkmtupdateoverlay
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTUpdateOverlay
 - d3dkmthk/D3DKMTUpdateOverlay
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
 - API-MS-Win-dx-d3dkmt-l1-1-0.dll
 - API-MS-Win-dx-d3dkmt-l1-1-1.dll
 - API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
 - D3DKMTUpdateOverlay
---

# D3DKMTUpdateOverlay function


## -description

The <b>D3DKMTUpdateOverlay</b> function modifies a kernel-mode overlay object.

## -parameters

### -param D3DKMT_UPDATEOVERLAY

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_updateoverlay">D3DKMT_UPDATEOVERLAY</a> structure that describes how to modify the overlay.

## -returns

<b>D3DKMTUpdateOverlay</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The kernel-mode overlay object was successfully modified. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display device was reset. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 
| **STATUS_NO_MEMORY** | [D3DKMTUpdateOverlay](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtupdateoverlay)  could not complete because of insufficient memory. | 

This function might also return other NTSTATUS values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_updateoverlay">D3DKMT_UPDATEOVERLAY</a>

