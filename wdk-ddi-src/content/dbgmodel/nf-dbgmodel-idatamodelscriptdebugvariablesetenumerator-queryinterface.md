---
UID: NF:dbgmodel.IDataModelScriptDebugVariableSetEnumerator.QueryInterface
title: IDataModelScriptDebugVariableSetEnumerator::QueryInterface (dbgmodel.h)
description: Retrieves pointers to the supported interfaces on an object. This method calls IUnknown::AddRef on the pointer it returns. 
ms.assetid: a5344740-740f-4417-9cd1-9b08fdde45d8
ms.date: 09/10/2018
keywords: ["IDataModelScriptDebugVariableSetEnumerator::QueryInterface"]
f1_keywords:
 - "dbgmodel/IDataModelScriptDebugVariableSetEnumerator.QueryInterface"
 - "IDataModelScriptDebugVariableSetEnumerator.QueryInterface"
ms.keywords: IDataModelScriptDebugVariableSetEnumerator::QueryInterface, QueryInterface, IDataModelScriptDebugVariableSetEnumerator.QueryInterface, IDataModelScriptDebugVariableSetEnumerator::QueryInterface, IDataModelScriptDebugVariableSetEnumerator.QueryInterface
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
- IDataModelScriptDebugVariableSetEnumerator.QueryInterface
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebugVariableSetEnumerator::QueryInterface


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
[IDataModelScriptDebugVariableSetEnumerator interface](nn-dbgmodel-idatamodelscriptdebugvariablesetenumerator.md)
