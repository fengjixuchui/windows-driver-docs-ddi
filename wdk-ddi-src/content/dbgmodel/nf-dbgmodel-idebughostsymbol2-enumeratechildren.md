---
UID: NF:dbgmodel.IDebugHostSymbol2.EnumerateChildren
title: IDebugHostSymbol2::EnumerateChildren (dbgmodel.h)
description: The EnumerateChildren method returns an enumerator which will enumerate all children of a given symbol.
ms.assetid: 498ad04b-feb3-4c5b-88fb-352110c0390e
ms.date: 09/20/2018
keywords: ["IDebugHostSymbol2::EnumerateChildren"]
ms.keywords: IDebugHostSymbol2::EnumerateChildren, EnumerateChildren, IDebugHostSymbol2.EnumerateChildren, IDebugHostSymbol2::EnumerateChildren, IDebugHostSymbol2.EnumerateChildren
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
 - IDebugHostSymbol2::EnumerateChildren
 - dbgmodel/IDebugHostSymbol2::EnumerateChildren
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostSymbol2.EnumerateChildren
---

# IDebugHostSymbol2::EnumerateChildren


## -description

The EnumerateChildren method returns an enumerator which will enumerate all children of a given symbol. For a C++ type, for example, the base classes, fields, member functions, and the like are all considered children of the type symbol.

## -parameters

### -param kind

Indicates what kinds of child symbols the caller wishes to enumerate. If the flat value Symbol is passed, all kinds of child symbols will be enumerated.

### -param name

If specified, only child symbols with a name as given in this argument will be enumerated.

### -param ppEnum

An enumerator which enumerates child symbols of the specified kind and name will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IDebugHostType2> spType; /* get the type of an object */

// Enumerate every field of this type.  Note thiat this *WILL NOT* enumerate 
// fields of base classes!
ComPtr<IDebugHostSymbolEnumerator> spEnum;
if (SUCCEEDED(spType->EnumerateChildren(SymbolField, nullptr, &spEnum)))
{
    ComPtr<IDebugHostSymbol> spFieldSymbol;
    HRESULT hr = S_OK;
    while (SUCCEEDED(hr))
    {
        hr = spEnum->GetNext(&spFieldSymbol);
        if (SUCCEEDED(hr))
        {
            ComPtr<IDebugHostField> spField;
            if (SUCCEEDED(spFieldSymbol.As(&spField))) /* should always succeed */
            {
                // spField is each field of the type in turn
            }
        }
    }

    // hr == E_BOUNDS : we hit the end of the enumerator
    // hr == E_ABORT  : user requested interruption, propagate upwards immediately
}
```

## -see-also

[IDebugHostSymbol2 interface](nn-dbgmodel-idebughostsymbol2.md)

