---
UID: NN:dbgmodel.IModelMethod
title: IModelMethod (dbgmodel.h)
description: Represents a method which can be called.
ms.assetid: 3483b979-a5a3-49ce-9036-3c021fa14b5b
ms.date: 07/16/2018
keywords: ["IModelMethod interface"]
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
 - IModelMethod
 - dbgmodel/IModelMethod
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IModelMethod
---

# IModelMethod interface


## -description

Represents a method which can be called.

Extensions which implement methods would implement this interface one or more times for the methods which it provides.

## -inheritance

IModelMethod interits from IUnknown.

## -remarks

A method in the data model is an implementation of the IModelMethod interface which is boxed into an [IModelObject](nn-dbgmodel-imodelobject.md). The model object will return a kind of ObjectMethod when queried and the intrinsic value is a VT_UNKNOWN which is guaranteed to be queryable for IModelMethod. In process, it is guaranteed to be statically castable to IModelMethod. 

All methods in the data model are dynamic in nature. They take as input a set of 0 or more arguments and return a single output value. There is no overload resolution and no metadata about parameter names, types, or expectations.

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)