---
UID: NF:dbgmodel.IDebugHostField.AddRef
title: IDebugHostField::AddRef (dbgmodel.h)
description: Increments the reference count for an interface on an object. This method should be called for every new copy of a pointer to an interface on an object.
ms.assetid: 4b267c26-6613-444b-a9c8-53e7a151acce
ms.date: 09/21/2018
keywords: ["IDebugHostField::AddRef"]
ms.keywords: IDebugHostField::AddRef, AddRef, IDebugHostField.AddRef, IDebugHostField::AddRef, IDebugHostField.AddRef
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
 - IDebugHostField::AddRef
 - dbgmodel/IDebugHostField::AddRef
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostField.AddRef
---

# IDebugHostField::AddRef


## -description

Increments the reference count for an interface on an object. This method should be called for every new copy of a pointer to an interface on an object. 

For more information, see [IUnknown::AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) and [Introduction to COM](/cpp/atl/introduction-to-com).

## -returns

This method returns ULONG.

## -remarks

## -see-also

[IDebugHostField interface](nn-dbgmodel-idebughostfield.md)