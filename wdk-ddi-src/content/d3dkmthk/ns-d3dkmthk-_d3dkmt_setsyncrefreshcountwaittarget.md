---
UID: NS:d3dkmthk._D3DKMT_SETSYNCREFRESHCOUNTWAITTARGET
title: _D3DKMT_SETSYNCREFRESHCOUNTWAITTARGET (d3dkmthk.h)
description: Used to set sync refresh count for wait target.
ms.assetid: 834d26e5-2c55-4716-8603-e0f7327f7937
ms.date: 10/19/2018
keywords: ["_D3DKMT_SETSYNCREFRESHCOUNTWAITTARGET structure"]
f1_keywords:
 - "d3dkmthk/_D3DKMT_SETSYNCREFRESHCOUNTWAITTARGET"
ms.keywords: _D3DKMT_SETSYNCREFRESHCOUNTWAITTARGET, D3DKMT_SETSYNCREFRESHCOUNTWAITTARGET, 
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DKMT_SETSYNCREFRESHCOUNTWAITTARGET
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dkmthk.h
api_name: 
- _D3DKMT_SETSYNCREFRESHCOUNTWAITTARGET
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# _D3DKMT_SETSYNCREFRESHCOUNTWAITTARGET structure

## -description

Used to set sync refresh count for wait target.

## -struct-fields

### -field hAdapter

[in] A handle to the graphics adapter.

### -field hDevice

[in, opt] A handle to the device.

### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the monitor is connected to.

### -field TargetSyncRefreshCount
 
[in] The target sync refresh count.

## -remarks

## -see-also
