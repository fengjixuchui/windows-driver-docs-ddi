---
UID: NC:d3dkmthk.PFND3DKMT_QUERYRESOURCEINFOFROMNTHANDLE
title: PFND3DKMT_QUERYRESOURCEINFOFROMNTHANDLE (d3dkmthk.h)
description: Maps a global NT handle to resource information that is needed for a call to the D3DKMTQueryResourceInfo function.
old-location: display\d3dkmtqueryresourceinfofromnthandle.htm
ms.assetid: 7a433aaf-3215-4d11-8989-2d7bdc7f7499
ms.date: 05/10/2018
keywords: ["PFND3DKMT_QUERYRESOURCEINFOFROMNTHANDLE callback function"]
ms.keywords: D3DKMTQueryResourceInfoFromNtHandle, D3DKMTQueryResourceInfoFromNtHandle callback function [Display Devices], PFND3DKMT_QUERYRESOURCEINFOFROMNTHANDLE, PFND3DKMT_QUERYRESOURCEINFOFROMNTHANDLE callback, d3dkmthk/D3DKMTQueryResourceInfoFromNtHandle, display.d3dkmtqueryresourceinfofromnthandle
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
 - PFND3DKMT_QUERYRESOURCEINFOFROMNTHANDLE
 - d3dkmthk/PFND3DKMT_QUERYRESOURCEINFOFROMNTHANDLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmthk.h
api_name:
 - D3DKMTQueryResourceInfoFromNtHandle
---

# PFND3DKMT_QUERYRESOURCEINFOFROMNTHANDLE callback function


## -description

Maps a global NT handle  to resource information that is needed for a call to the <a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtqueryresourceinfo">D3DKMTQueryResourceInfo</a> function.

## -parameters

### -param Arg1

*pData* 

[in, out] A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_queryresourceinfofromnthandle">D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE</a> structure that describes information that is required to perform the mapping.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The mapping was performed successfully.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|


This function might also return other NTSTATUS values.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtqueryresourceinfo">D3DKMTQueryResourceInfo</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_queryresourceinfofromnthandle">D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE</a>