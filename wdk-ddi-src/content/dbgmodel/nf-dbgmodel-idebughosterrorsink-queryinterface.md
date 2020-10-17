---
UID: NF:dbgmodel.IDebugHostErrorSink.QueryInterface
title: IDebugHostErrorSink::QueryInterface (dbgmodel.h)
description: Retrieves pointers to the supported interfaces on an object. This method calls IUnknown::AddRef on the pointer it returns.
ms.assetid: 3166599e-94ec-4ca7-b883-b8353ced57f0
ms.date: 09/12/2018
keywords: ["IDebugHostErrorSink::QueryInterface"]
ms.keywords: IDebugHostErrorSink::QueryInterface, QueryInterface, IDebugHostErrorSink.QueryInterface, IDebugHostErrorSink::QueryInterface, IDebugHostErrorSink.QueryInterface
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
 - IDebugHostErrorSink::QueryInterface
 - dbgmodel/IDebugHostErrorSink::QueryInterface
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostErrorSink.QueryInterface
---

# IDebugHostErrorSink::QueryInterface


## -description

Retrieves pointers to the supported interfaces on an object. This method calls IUnknown::AddRef on the pointer it returns. 

For more information, see [IUnknown::QueryInterface](/windows/win32/api/Unknwn/nf-unknwn-iunknown-queryinterface(refiid_void)) and [Introduction to COM](/cpp/atl/introduction-to-com).

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

[IDebugHostErrorSink interface](nn-dbgmodel-idebughosterrorsink.md)