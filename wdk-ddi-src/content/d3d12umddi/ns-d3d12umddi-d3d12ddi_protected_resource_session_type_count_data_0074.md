---
UID: NS:d3d12umddi.D3D12DDI_PROTECTED_RESOURCE_SESSION_TYPE_COUNT_DATA_0074
title: D3D12DDI_PROTECTED_RESOURCE_SESSION_TYPE_COUNT_DATA_0074
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
ms.assetid: 0729f26c-ae31-4617-911d-5b71c7d4bf14
tech.root: display
description: Count of protected resource session types.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_PROTECTED_RESOURCE_SESSION_TYPE_COUNT_DATA_0074
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_PROTECTED_RESOURCE_SESSION_TYPE_COUNT_DATA_0074
f1_keywords:
 - D3D12DDI_PROTECTED_RESOURCE_SESSION_TYPE_COUNT_DATA_0074
 - d3d12umddi/D3D12DDI_PROTECTED_RESOURCE_SESSION_TYPE_COUNT_DATA_0074
dev_langs:
 - c++
---

## -description

Count of protected resource session types.

## -struct-fields

### -field NodeIndex

[in] In multi-adapter operation, **NodeIndex** indicates which physical adapter of the device this operation applies to.

### -field Count

[out] Number of protected resource session types supported by the driver.

## -remarks

See the [Protected Resources Specification](https://microsoft.github.io/DirectX-Specs/d3d/ProtectedResources.html) for more information.

## -see-also

[**D3D112DDICAPS_TYPE**](ne-d3d12umddi-d3d12ddicaps_type.md)

