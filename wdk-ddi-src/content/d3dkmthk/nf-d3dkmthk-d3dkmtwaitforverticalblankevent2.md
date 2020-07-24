---
UID: NF:d3dkmthk.D3DKMTWaitForVerticalBlankEvent2
title: D3DKMTWaitForVerticalBlankEvent2 function (d3dkmthk.h)
description: Waits for specified wait objects, including a vertical blank event, to occur and then returns. Supported starting with Windows 8.
old-location: display\d3dkmtwaitforverticalblankevent2.htm
ms.assetid: 71a48c1f-1eca-4f3e-a085-99ffc207a7e0
ms.date: 05/10/2018
keywords: ["D3DKMTWaitForVerticalBlankEvent2 function"]
ms.keywords: D3DKMTWaitForVerticalBlankEvent2, D3DKMTWaitForVerticalBlankEvent2 function [Display Devices], d3dkmthk/D3DKMTWaitForVerticalBlankEvent2, display.d3dkmtwaitforverticalblankevent2
f1_keywords:
 - "d3dkmthk/D3DKMTWaitForVerticalBlankEvent2"
 - "D3DKMTWaitForVerticalBlankEvent2"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.lib: Gdi32.lib 
req.dll: Gdi32.dll 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Gdi32.dll
api_name:
- D3DKMTWaitForVerticalBlankEvent2
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTWaitForVerticalBlankEvent2 function

## -description

Waits for specified wait objects, including a vertical blank event, to occur and then returns. Supported starting with Windows 8.

## -parameters

### -param D3DKMT_WAITFORVERTICALBLANKEVENT2

[in] Specifies parameters for waiting on multiple wait objects, including a vertical blank event.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_WAIT_0|The vertical blank event caused the wait object to return.|
|STATUS_WAIT_1–STATUS_WAIT_8|The number of the user-mode event that caused the wait object to return.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
