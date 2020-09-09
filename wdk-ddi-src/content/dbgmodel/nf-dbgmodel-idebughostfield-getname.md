---
UID: NF:dbgmodel.IDebugHostField.GetName
title: IDebugHostField::GetName (dbgmodel.h)
description: Returns the name of the symbol if the symbol has a name.
ms.assetid: 9b946d62-a11a-4007-a0fb-92b75b7c589f
ms.date: 09/12/2018
keywords: ["IDebugHostField::GetName"]
ms.keywords: IDebugHostField::GetName, GetName, IDebugHostField.GetName, IDebugHostField::GetName, IDebugHostField.GetName
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
 - IDebugHostField::GetName
 - dbgmodel/IDebugHostField::GetName
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostField.GetName
---

# IDebugHostField::GetName


## -description

Returns the name of the symbol if the symbol has a name.  If the symbol does not have a name, an error is returned.

## -parameters

### -param symbolName

The name of the symbol will be returned here as a string allocated via the SysAllocString method.  The caller is responsible for freeing the allocated string via the SysFreeString method.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostField interface](nn-dbgmodel-idebughostfield.md)

