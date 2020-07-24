---
UID: NF:dbgmodel.IDebugHostConstant.GetContainingModule
title: IDebugHostConstant::GetContainingModule (dbgmodel.h)
description: Returns the module which contains this symbol if the symbol has a containing module.
ms.assetid: 1f192cdf-849a-4679-92f2-3ca538e3841e
ms.date: 09/21/2018
keywords: ["IDebugHostConstant::GetContainingModule"]
f1_keywords:
 - "dbgmodel/IDebugHostConstant.GetContainingModule"
 - "IDebugHostConstant.GetContainingModule"
ms.keywords: IDebugHostConstant::GetContainingModule, GetContainingModule, IDebugHostConstant.GetContainingModule, IDebugHostConstant::GetContainingModule, IDebugHostConstant.GetContainingModule
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
- IDebugHostConstant.GetContainingModule
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostConstant::GetContainingModule


## -description

Returns the module which contains this symbol if the symbol has a containing module.  If the symbol does not have a containing module, an error is returned.
    
## -parameters

### -param containingModule
The module which contains the symbol will be returned here.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also
[IDebugHostConstant interface](nn-dbgmodel-idebughostconstant.md)
