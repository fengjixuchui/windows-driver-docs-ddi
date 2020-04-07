---
UID: NF:dbgmodel.IDebugHostSymbol2.QueryInterface
title: IDebugHostSymbol2::QueryInterface (dbgmodel.h)
description: Retrieves pointers to the supported interfaces on an object. This method calls IUnknown::AddRef on the pointer it returns. 
ms.assetid: 700638e0-73ae-4689-930a-14a925a48ee7
ms.date: 09/20/2018
keywords: ["IDebugHostSymbol2::QueryInterface"]
f1_keywords:
 - "dbgmodel/IDebugHostSymbol2.QueryInterface"
ms.keywords: IDebugHostSymbol2::QueryInterface, QueryInterface, IDebugHostSymbol2.QueryInterface, IDebugHostSymbol2::QueryInterface, IDebugHostSymbol2.QueryInterface
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
- IDebugHostSymbol2.QueryInterface
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostSymbol2::QueryInterface


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

[IDebugHostSymbol2 interface](nn-dbgmodel-idebughostsymbol2.md)
