---
UID: NF:dbgmodel.IDataModelManager2.CreateSyntheticObject
title: IDataModelManager2::CreateSyntheticObject (dbgmodel.h)
description: The CreateSyntheticObject method creates an empty data model object -- a dictionary of key/value/metadata tuples and concepts.
ms.assetid: 039a1b6e-6b9d-47fd-9c18-c65640daca3a
ms.date: 09/11/2018
keywords: ["IDataModelManager2::CreateSyntheticObject"]
f1_keywords:
 - "dbgmodel/IDataModelManager2.CreateSyntheticObject"
ms.keywords: IDataModelManager2::CreateSyntheticObject, CreateSyntheticObject, IDataModelManager2.CreateSyntheticObject, IDataModelManager2::CreateSyntheticObject, IDataModelManager2.CreateSyntheticObject
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
- IDataModelManager2.CreateSyntheticObject
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelManager2::CreateSyntheticObject

## -description

The CreateSyntheticObject method creates an empty data model object -- a dictionary of key/value/metadata tuples and concepts. At the time of creation, there are no keys nor concepts on the object. It is a clean slate for the caller to utilize. 

## -parameters

### -param context
The debug host context which will be associated with the newly created synthetic object. Not every object requires a context. If the object refers to things such as processes, threads, or memory in the address space of the host, it may need one (unless it encapsulates other objects which contain such).


### -param object
The newly created object will be returned here.


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDataModelManager> spManager; /* get the data model manager */

ComPtr<IModelObject> spNewObject;
if (SUCCEEDED(spManager->CreateSyntheticObject(nullptr, &spNewObject)))
{
     // spNewObject is an empty object (a dictionary of key/value/metadata tuples)
}
```

## -see-also

[IDataModelManager2 interface](nn-dbgmodel-idatamodelmanager2.md)
