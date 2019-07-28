---
UID: NF:dbgmodel.IDebugHostEvaluator2.QueryInterface
title: IDebugHostEvaluator2::QueryInterface (dbgmodel.h)
description: Retrieves pointers to the supported interfaces on an object. This method calls IUnknown::AddRef on the pointer it returns. 
ms.assetid: 39b286b2-8dd6-4698-9920-0a25c1acad97
ms.date: 09/12/2018
ms.topic: method
f1_keywords:
 - "dbgmodel/IDebugHostEvaluator2.QueryInterface"
ms.keywords: IDebugHostEvaluator2::QueryInterface, QueryInterface, IDebugHostEvaluator2.QueryInterface, IDebugHostEvaluator2::QueryInterface, IDebugHostEvaluator2.QueryInterface
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
topic_type: 
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDebugHostEvaluator2.QueryInterface
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostEvaluator2::QueryInterface


## -description

Retrieves pointers to the supported interfaces on an object. This method calls IUnknown::AddRef on the pointer it returns. 

For more information, see [IUnknown::QueryInterface](https://docs.microsoft.com/windows/desktop/api/Unknwn/nf-unknwn-iunknown-queryinterface(refiid_void)) and [Introduction to COM](https://docs.microsoft.com/cpp/atl/introduction-to-com).


## -parameters

### -param iid
The interface ID. A pointer to an existing object provided as input. 

### -param iface
The returned pointer to the requested COM interface. 


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

Standard COM method.

## -see-also

[IDebugHostEvaluator2 interface](nn-dbgmodel-idebughostevaluator2.md)
