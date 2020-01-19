---
UID: NF:d3dkmthk.D3DKMTGetMultisampleMethodList
title: D3DKMTGetMultisampleMethodList function (d3dkmthk.h)
description: The D3DKMTGetMultisampleMethodList function retrieves a list of multiple-sample methods that are used for an allocation.
old-location: display\d3dkmtgetmultisamplemethodlist.htm
ms.assetid: 10084238-dfeb-42a5-9bf0-06cb9b4f440c
ms.date: 05/10/2018
ms.keywords: D3DKMTGetMultisampleMethodList, D3DKMTGetMultisampleMethodList function [Display Devices], OpenGL_Functions_8adebfdd-1a02-4e17-8aef-e183587202d2.xml, d3dkmthk/D3DKMTGetMultisampleMethodList, display.d3dkmtgetmultisamplemethodlist
ms.topic: function
f1_keywords:
 - "d3dkmthk/D3DKMTGetMultisampleMethodList"
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
- D3DKMTGetMultisampleMethodList
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTGetMultisampleMethodList function

## -description

The <b>D3DKMTGetMultisampleMethodList</b> function retrieves a list of multiple-sample methods that are used for an allocation.

## -parameters

### -param Arg1

*pData* 

[in, out] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_getmultisamplemethodlist">D3DKMT_GETMULTISAMPLEMETHODLIST</a> structure that describes the list of multiple-sample methods for an allocation.

## -returns

<b>D3DKMTGetMultisampleMethodList</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The list of multiple-sample methods was successfully retrieved.|
|STATUS_DEVICE_REMOVED|The graphics adapter was stopped.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other NTSTATUS values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_getmultisamplemethodlist">D3DKMT_GETMULTISAMPLEMETHODLIST</a>
 

 

