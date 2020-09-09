---
UID: NF:dbgmodel.IModelObject.Compare
title: IModelObject::Compare (dbgmodel.h)
description: The Compare method compares two model objects and returns an indication of how those objects relate.
ms.assetid: 18bf4d91-bbd6-4c5a-8b21-962fbd94c8fb
ms.date: 07/20/2018
keywords: ["IModelObject::Compare"]
ms.keywords: IModelObject::Compare, Compare, IModelObject.Compare, IModelObject::Compare, IModelObject.Compare
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
 - IModelObject::Compare
 - dbgmodel/IModelObject::Compare
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IModelObject.Compare
---

# IModelObject::Compare


## -description

The Compare method compares two model objects and returns an indication of how those objects relate. One of three states is returned:

```text
	< 0: (this < other)

	== 0: (this == other)

	> 0: (this > other)
```

Note that only intrinsic values can be compared using this method. Calling with any other object type will result in failure.

## -parameters

### -param other

The object to compare this object to. The instance object is on the left side of the comparison and the object supplied by this argument is on the right.

### -param ppResult

The result of the comparison is returned here. If less than zero, this < other; if equal to zero, this == other; if greater than zero, this > other.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IModelObject> spValue1; /* get some ordinal */
ComPtr<IModelObject> spValue2; /* get some other ordinal */

ComPtr<IModelObject> spResult;
if (SUCCEEDED(spValue1->Compare(spValue2.Get(), &spResult)))
{
    VARIANT vtVal;
    if (SUCCEEDED(spResult->GetIntrinsicValueAs(VT_I4, &vtVal)))
    {
        int compVal = vtVal.lVal;

        // compVal < 0 : spValue1 < spValue2
        // compVal == 0: spValue1 == spValue2
        // compVal > 0 : spValue1 > spValue2
    }
}
```

## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)

