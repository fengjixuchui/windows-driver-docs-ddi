---
UID: NF:dbgmodel.IDataModelManager2.UnregisterModelForTypeSignature
title: IDataModelManager2::UnregisterModelForTypeSignature (dbgmodel.h)
description: The UnregisterModelForTypeSignature method undoes a prior call to the RegisterModelForTypeSignature method. 
ms.assetid: 9b378c81-3ed3-4565-98c0-0dfd658c8fcc
ms.date: 09/11/2018
keywords: ["IDataModelManager2::UnregisterModelForTypeSignature"]
f1_keywords:
 - "dbgmodel/IDataModelManager2.UnregisterModelForTypeSignature"
ms.keywords: IDataModelManager2::UnregisterModelForTypeSignature, UnregisterModelForTypeSignature, IDataModelManager2.UnregisterModelForTypeSignature, IDataModelManager2::UnregisterModelForTypeSignature, IDataModelManager2.UnregisterModelForTypeSignature
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
- IDataModelManager2.UnregisterModelForTypeSignature
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelManager2::UnregisterModelForTypeSignature


## -description

The UnregisterModelForTypeSignature method undoes a prior call to the RegisterModelForTypeSignature method. This method can either remove a given data model as the canonical visualizer for types matching a particular type signature or it can remove a given data model as the canonical visualizer for every type signature under which that data model is registered. 

## -parameters

### -param dataModel
The data model to be unregistered as the canonical visualizer for one or more type signatures. If the typeSignature argument is nullptr, this data model will be unregistered from all type signatures it was registered against; otherwise, it will only be unregistered against the particular type signature indicated.

### -param typeSignature
The type signature against which the data model given by the dataModel argument will be unregistered. This argument is optional and hence, nullptr can be passed. If nullptr is passed, the data model given by the dataModel argument will be unregistered from all type signatures it was registered against.



## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDataModelManager2> spManager;             /* get the data model manager */
ComPtr<IDebugHostTypeSignature> spTypeSignature; /* get a type signature (see
                                                    RegisterModelForTypeSignature) */
ComPtr<IModelObject> spDataModelObject;          /* get a data model object (see
                                                    CreateDataModelObject) */

if (SUCCEEDED(spManager->UnregisterModelForTypeSignature(spDataModelObject.Get(),
                                                         spTypeSignature.Get())))
{
    // spDataModelObject is no longer registered as the canonical visualizer
    // for types matching the signature.  Note that if the second argument were 
    // passed as 'nullptr', spDataModelObject would no longer be registered 
    // as the canonical visualizer for *ANY* types.
}
```
## -see-also

[IDataModelManager2 interface](nn-dbgmodel-idatamodelmanager2.md)
