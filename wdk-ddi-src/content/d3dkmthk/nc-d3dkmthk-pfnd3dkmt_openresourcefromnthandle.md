---
UID: NC:d3dkmthk.PFND3DKMT_OPENRESOURCEFROMNTHANDLE
title: PFND3DKMT_OPENRESOURCEFROMNTHANDLE (d3dkmthk.h)
description: Opens a shared resource from an NT handle.
old-location: display\d3dkmtopenresourcefromnthandle.htm
ms.assetid: d5a66102-782a-482e-8119-48015820d0c7
ms.date: 05/10/2018
keywords: ["PFND3DKMT_OPENRESOURCEFROMNTHANDLE callback function"]
ms.keywords: D3DKMTOpenResourceFromNtHandle, D3DKMTOpenResourceFromNtHandle callback function [Display Devices], PFND3DKMT_OPENRESOURCEFROMNTHANDLE, PFND3DKMT_OPENRESOURCEFROMNTHANDLE callback, d3dkmthk/D3DKMTOpenResourceFromNtHandle, display.d3dkmtopenresourcefromnthandle
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3DKMT_OPENRESOURCEFROMNTHANDLE
 - d3dkmthk/PFND3DKMT_OPENRESOURCEFROMNTHANDLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmthk.h
api_name:
 - D3DKMTOpenResourceFromNtHandle
---

# PFND3DKMT_OPENRESOURCEFROMNTHANDLE callback function


## -description

Opens a shared resource from an NT handle.

## -parameters

### -param Arg1

*pData* 

[in, out] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_openresourcefromnthandle">D3DKMT_OPENRESOURCEFROMNTHANDLE</a> structure that describes information required to open a shared resource.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function completed successfully.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other NTSTATUS values.

## -remarks

The NT handle to the process, which is used as the <b>hNtHandle</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_openresourcefromnthandle">D3DKMT_OPENRESOURCEFROMNTHANDLE</a> structure, is typically acquired by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtshareobjects">D3DKMTShareObjects</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopennthandlefromname">D3DKMTOpenNtHandleFromName</a>  functions.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopennthandlefromname">D3DKMTOpenNtHandleFromName</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtshareobjects">D3DKMTShareObjects</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_openresourcefromnthandle">D3DKMT_OPENRESOURCEFROMNTHANDLE</a>

