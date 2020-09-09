---
UID: NF:dbgmodel.IDebugHostType2.GetFunctionParameterTypeAt
title: IDebugHostType2::GetFunctionParameterTypeAt (dbgmodel.h)
description: The GetFunctionParameterTypeAt method returns the type of the i-th argument to the function.
ms.assetid: 7e0e1d0c-519b-4acf-ba48-8231f5235058
ms.date: 09/20/2018
keywords: ["IDebugHostType2::GetFunctionParameterTypeAt"]
ms.keywords: IDebugHostType2::GetFunctionParameterTypeAt, GetFunctionParameterTypeAt, IDebugHostType2.GetFunctionParameterTypeAt, IDebugHostType2::GetFunctionParameterTypeAt, IDebugHostType2.GetFunctionParameterTypeAt
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
 - IDebugHostType2::GetFunctionParameterTypeAt
 - dbgmodel/IDebugHostType2::GetFunctionParameterTypeAt
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType2.GetFunctionParameterTypeAt
---

# IDebugHostType2::GetFunctionParameterTypeAt


## -description

The GetFunctionParameterTypeAt method returns the type of the i-th argument to the function.

## -parameters

### -param i

A zero based index into the function argument list for which to retrieve the argument type.

### -param parameterType

The type of the i-th argument to the function will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostType> spType; /* get a type for a function (see FindTypeByName) */

// enumerate (in order) the types of parameters the function takes
ULONG64 count;
if (SUCCEEDED(spType->GetFunctionParameterTypeCount(&count)))
{
    for (ULONG64 i = 0; i < count; ++i)
    {
        ComPtr<IDebugHostType> spParamType;
        if (SUCCEEDED(spType->GetFunctionParameterTypeAt(i, &spParamType)))
        {
            // spParamType is the type symbol for the type of parameter the 
            // function takes at position i in the argument list.
        }
    }
}
```

## -see-also

[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)

