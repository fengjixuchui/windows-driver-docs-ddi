---
UID: NF:dbgmodel.IDebugHostType.AddRef
title: IDebugHostType::AddRef (dbgmodel.h)
description: Increments the reference count for an interface on an object. This method should be called for every new copy of a pointer to an interface on an object.
ms.assetid: 846fe632-229e-421d-84d9-f293ec1d2d34
ms.date: 09/21/2018
keywords: ["IDebugHostType::AddRef"]
ms.keywords: IDebugHostType::AddRef, AddRef, IDebugHostType.AddRef, IDebugHostType::AddRef, IDebugHostType.AddRef
req.header: dbgmodel.h
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDebugHostType::AddRef
 - dbgmodel/IDebugHostType::AddRef
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType.AddRef
---

# IDebugHostType::AddRef


## -description

Increments the reference count for an interface on an object. This method should be called for every new copy of a pointer to an interface on an object. 

For more information, see [IUnknown::AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) and [Introduction to COM](/cpp/atl/introduction-to-com).

## -returns

This method returns ULONG.

## -remarks

## -see-also

[IDebugHostType interface](nn-dbgmodel-idebughosttype.md)