---
UID: NF:dispmprt.DlEnumerateChildren
title: DlEnumerateChildren function
author: windows-driver-content
description: Allows a miniport driver to force a re-enumeration of its child devices.
tech.root: display
ms.assetid: 3d97741f-870d-4018-870f-2c4aecf960de
ms.author: windowsdriverdev
ms.date: 04/04/2019 
keywords: ["DlEnumerateChildren function"]
f1_keywords:
 - "dispmprt/DlEnumerateChildren"
ms.keywords: DlEnumerateChildren
req.header: dispmprt.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- DllExport
api_location: 
- Displib.lib
- Displib.dll
api_name: 
- DlEnumerateChildren
product: 
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# DlEnumerateChildren function


## -description

Allows a miniport driver to force a re-enumeration of its child devices.

## -parameters

### -param DeviceHandle

Pointer to a device handle.

### -param Reserved

Reserved.


## -returns

This function returns VP_STATUS.

## -remarks

## -see-also
