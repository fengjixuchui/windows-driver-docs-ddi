---
UID: NN:dbgmodel.IKeyStore
title: IKeyStore (dbgmodel.h)
description: A key/value store.  Typically used for metadata.
ms.assetid: 434182b4-c9ee-4ca0-b092-f60098df5d16
ms.date: 07/16/2018
keywords: ["IKeyStore interface"]
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
 - IKeyStore
 - dbgmodel/IKeyStore
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IKeyStore
---

# IKeyStore interface


## -description

A key/value store.  Typically used for metadata.

## -inheritance

IKeyStore interits from IUnknown.

## -remarks

**Metadata in the Data Model**

One of the core notions in the data model is that an object (particularly a synthetic one) is a dictionary of key/value/metadata tuples. Each key can have an entire store of metadata associated with it that describes a variety of things surrounding the key and its potential value. Note that the metadata does not, in any way, change the value of the key. It is only ancillary information associated with the key and its value which may affect the presentation or other associated attributes of the key and its value. 

In some senses, a metadata store is not all that different from the key/value/metadata tuples that are the essence of an object in the data model. It is, however, simplified from this view. A metadata store is represented by the *IKeyStore* interface. While also a collection of key/value/metadata tuples, there are limitations to what can be done with a metadata key store versus a model object: 

- A key store can only have a single parent store -- it cannot have an arbitrary chain of parent models.
- A key store has no concepts. It can only have the dictionary of key/value/metadata tuples. This means that the keys present in a key store are static. They can not be created on demand by a dynamic language system.
- By convention only, the values in a metadata defined key store are restricted to basic values (intrinsics and property accessors)

While a key store can have an arbitrary number (and arbitrary naming) of keys, there are certain names that have defined semantic values. For a list of those values, see [Debugger Data Model Metadata Interfaces](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-additional-interfaces#-debugger-data-model-metadata-interfaces).

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)

