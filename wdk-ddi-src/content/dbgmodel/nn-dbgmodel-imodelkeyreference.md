---
UID: NN:dbgmodel.IModelKeyReference
title: IModelKeyReference (dbgmodel.h)
description: A reference to a key on a data model object.
ms.assetid: f92f8963-479b-4f90-abef-5ad227e8781c
ms.date: 07/16/2018
keywords: ["IModelKeyReference interface"]
req.header: dbgmodel.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.umdf-ver: 
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
 - IModelKeyReference
 - dbgmodel/IModelKeyReference
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IModelKeyReference
---

# IModelKeyReference interface


## -description

A reference to a key on a data model object.

## -inheritance

IModelKeyReference interits from IUnknown.

## -remarks

**Key References** 

A key reference is, in essence, a handle to a key on a particular object. A client can retrieve such handle via methods such as GetKeyReference and use the handle later to get or set the value of the key without necessarily holding onto the original object. This type of object is an implementation of the IModelKeyReference or [IModelKeyReference2](nn-dbgmodel-imodelkeyreference2.md) interface which is boxed into an [IModelObject](nn-dbgmodel-imodelobject.md). The model object will return a kind of ObjectKeyReference when queried and then intrinsic value is a VT_UNKNOWN which is guaranteed to be queryable for IModelKeyReference. In process, it is guaranteed to be statically castable to IModelKeyReference.

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)