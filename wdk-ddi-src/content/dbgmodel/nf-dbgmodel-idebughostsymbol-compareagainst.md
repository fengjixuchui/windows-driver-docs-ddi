---
UID: NF:dbgmodel.IDebugHostSymbol.CompareAgainst
title: IDebugHostSymbol::CompareAgainst (dbgmodel.h)
description: Compares two symbols for equality. 
ms.assetid: 00afbd6a-9157-43b3-a449-fa9aa6f50fab
ms.date: 09/11/2018
keywords: ["IDebugHostSymbol::CompareAgainst"]
f1_keywords:
 - "dbgmodel/IDebugHostSymbol.CompareAgainst"
ms.keywords: IDebugHostSymbol::CompareAgainst, CompareAgainst, IDebugHostSymbol.CompareAgainst, IDebugHostSymbol::CompareAgainst, IDebugHostSymbol.CompareAgainst
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
- IDebugHostSymbol.CompareAgainst
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostSymbol::CompareAgainst


## -description

Compares two symbols for equality.  A host is under no obligation to ensure that there is interface pointer equality for two identical symbols.  This can be used to check for equality. 

Note that presently, "comparisonFlags" is reserved.

## -parameters

### -param pComparisonSymbol
The symbol to compare against.

### -param comparisonFlags
Reserved.  Must be set to 0.

### -param pMatches
An indication of whether the symbols are equal will be returned here.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostSymbol interface](nn-dbgmodel-idebughostsymbol.md)
