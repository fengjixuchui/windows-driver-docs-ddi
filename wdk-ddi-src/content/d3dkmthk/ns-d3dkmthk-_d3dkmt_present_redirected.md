---
UID: NS:d3dkmthk._D3DKMT_PRESENT_REDIRECTED
title: _D3DKMT_PRESENT_REDIRECTED (d3dkmthk.h)
description: Used to give information on the status of the present history token.
old-location: display\d3dkmt-present-redirected.htm
ms.assetid: a883d80a-0240-4a2a-b3d8-ca87080717ee
ms.date: 05/10/2018
keywords: ["D3DKMT_PRESENT_REDIRECTED structure"]
ms.keywords: D3DKMT_PRESENT_REDIRECTED, D3DKMT_PRESENT_REDIRECTED structure [Display Devices], _D3DKMT_PRESENT_REDIRECTED, d3dkmthk/D3DKMT_PRESENT_REDIRECTED, display.d3dkmt-present-redirected
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: D3DKMT_PRESENT_REDIRECTED
f1_keywords:
 - _D3DKMT_PRESENT_REDIRECTED
 - d3dkmthk/_D3DKMT_PRESENT_REDIRECTED
 - D3DKMT_PRESENT_REDIRECTED
 - d3dkmthk/D3DKMT_PRESENT_REDIRECTED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMT_PRESENT_REDIRECTED
---

# _D3DKMT_PRESENT_REDIRECTED structure


## -description

Used to give information on the status of the present history token.

## -struct-fields

### -field hDevice

[in] Device associated with the present

### -field hSyncObj

[in] The sync object that the PHT waits on.

### -field WaitedFenceValue

[in] The fence value of hSyncObj that PHT waits on

### -field PresentHistoryToken

[in] The present history token.

### -field Flags

The flags needed to give the status of the present history token.

### -field hSource

[in] Source allocation to present from

### -field PrivateDriverDataSize

[in] The size of pPrivateDriverData.

### -field pPrivateDriverData

[in] Private driver data to pass to DdiPresent and DdiSetVidPnSourceAddress

