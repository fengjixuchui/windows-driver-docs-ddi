---
UID: NF:dbgmodel.IDebugHostType.GetContainingModule
title: IDebugHostType::GetContainingModule (dbgmodel.h)
description: Returns the module which contains this symbol if the symbol has a containing module.
ms.assetid: 8aba42ca-72d0-45fd-b2e7-ade953081f49
ms.date: 09/21/2018
keywords: ["IDebugHostType::GetContainingModule"]
f1_keywords:
 - "dbgmodel/IDebugHostType.GetContainingModule"
ms.keywords: IDebugHostType::GetContainingModule, GetContainingModule, IDebugHostType.GetContainingModule, IDebugHostType::GetContainingModule, IDebugHostType.GetContainingModule
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
- IDebugHostType.GetContainingModule
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostType::GetContainingModule


## -description

Returns the module which contains this symbol if the symbol has a containing module.  If the symbol does not have a containing module, an error is returned.

## -parameters

### -param containingModule
The module which contains the symbol will be returned here.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostType interface](nn-dbgmodel-idebughosttype.md)
