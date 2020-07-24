---
UID: NF:dbgmodel.IHostDataModelAccess.QueryInterface
title: IHostDataModelAccess::QueryInterface (dbgmodel.h)
description: Retrieves pointers to the supported interfaces on an object. This method calls IUnknown::AddRef on the pointer it returns. 
ms.assetid: a0f894dc-1518-4994-af6d-746f75f1b6d9
ms.date: 07/20/2018
keywords: ["IHostDataModelAccess::QueryInterface"]
f1_keywords:
 - "dbgmodel/IHostDataModelAccess.QueryInterface"
 - "IHostDataModelAccess.QueryInterface"
ms.keywords: IHostDataModelAccess::QueryInterface, QueryInterface, IHostDataModelAccess.QueryInterface, IHostDataModelAccess::QueryInterface, IHostDataModelAccess.QueryInterface
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
- IHostDataModelAccess.QueryInterface
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IHostDataModelAccess::QueryInterface


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

[IDataHostModelAccess interface](nn-dbgmodel-ihostdatamodelaccess.md)
