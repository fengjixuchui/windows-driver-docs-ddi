---
UID: NF:dbgmodel.IDebugHostPublic.GetType
title: IDebugHostPublic::GetType (dbgmodel.h)
description: Returns the type (e.g. "int *") of the symbol if the symbol has a type.
ms.assetid: abd64f47-aa14-42ce-8d89-4c8fc33fd045
ms.date: 09/18/2018
ms.topic: method
f1_keywords:
 - "dbgmodel/IDebugHostPublic.GetType"
ms.keywords: IDebugHostPublic::GetType, GetType, IDebugHostPublic.GetType, IDebugHostPublic::GetType, IDebugHostPublic.GetType
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
- IDebugHostPublic.GetType
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostPublic::GetType


## -description
Returns the type (e.g.: "int *") of the symbol if the symbol has a type.  If the symbol does not have a type, an error is returned.
 
## -parameters

### -param type
The type of the symbol will be returned here.

## -returns
This method returns HRESULT that indicates success or failure.


## -remarks

## -see-also

[IDebugHostPublic interface](nn-dbgmodel-idebughostpublic.md)
