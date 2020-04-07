---
UID: NF:dbgmodel.IDataModelScriptDebugStackFrame.QueryInterface
title: IDataModelScriptDebugStackFrame::QueryInterface (dbgmodel.h)
description: Retrieves pointers to the supported interfaces on an object. This method calls IUnknown::AddRef on the pointer it returns. 
ms.assetid: 382a3ad3-d35b-46d1-aeaf-746d84be6fcb
ms.date: 09/10/2018
keywords: ["IDataModelScriptDebugStackFrame::QueryInterface"]
f1_keywords:
 - "dbgmodel/IDataModelScriptDebugStackFrame.QueryInterface"
ms.keywords: IDataModelScriptDebugStackFrame::QueryInterface, QueryInterface, IDataModelScriptDebugStackFrame.QueryInterface, IDataModelScriptDebugStackFrame::QueryInterface, IDataModelScriptDebugStackFrame.QueryInterface
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
- IDataModelScriptDebugStackFrame.QueryInterface
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebugStackFrame::QueryInterface


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
[IDataModelScriptDebugStackFrame interface](nn-dbgmodel-idatamodelscriptdebugstackframe.md)
