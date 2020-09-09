---
UID: NF:dbgmodel.IDataModelNameBinder.QueryInterface
title: IDataModelNameBinder::QueryInterface (dbgmodel.h)
description: Retrieves pointers to the supported interfaces on an object. This method calls IUnknown::AddRef on the pointer it returns.
ms.assetid: 30c88578-1a85-4127-8e4b-446931a60e29
ms.date: 09/12/2018
keywords: ["IDataModelNameBinder::QueryInterface"]
ms.keywords: IDataModelNameBinder::QueryInterface, QueryInterface, IDataModelNameBinder.QueryInterface, IDataModelNameBinder::QueryInterface, IDataModelNameBinder.QueryInterface
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
 - IDataModelNameBinder::QueryInterface
 - dbgmodel/IDataModelNameBinder::QueryInterface
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelNameBinder.QueryInterface
---

# IDataModelNameBinder::QueryInterface


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

[IDataModelNameBinder interface](nn-dbgmodel-idatamodelnamebinder.md)

