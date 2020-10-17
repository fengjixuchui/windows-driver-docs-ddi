---
UID: NF:dbgmodel.IPreferredRuntimeTypeConcept.QueryInterface
title: IPreferredRuntimeTypeConcept::QueryInterface (dbgmodel.h)
description: The CastToPreferredRuntimeType method is called whenever a client wishes to attempt to convert from a static type instance to the runtime type of that instance.
ms.assetid: 4bb3fbdc-d1f0-4410-b289-3344d64cb051
ms.date: 09/20/2018
keywords: ["IPreferredRuntimeTypeConcept::QueryInterface"]
ms.keywords: IPreferredRuntimeTypeConcept::QueryInterface, QueryInterface, IPreferredRuntimeTypeConcept.QueryInterface, IPreferredRuntimeTypeConcept::QueryInterface, IPreferredRuntimeTypeConcept.QueryInterface
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
 - IPreferredRuntimeTypeConcept::QueryInterface
 - dbgmodel/IPreferredRuntimeTypeConcept::QueryInterface
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IPreferredRuntimeTypeConcept.QueryInterface
---

# IPreferredRuntimeTypeConcept::QueryInterface


## -description

Retrieves pointers to the supported interfaces on an object. This method calls IUnknown::AddRef on the pointer it returns. 

For more information, see [IUnknown::QueryInterface](/windows/win32/api/Unknwn/nf-unknwn-iunknown-queryinterface(refiid_void)) and [Introduction to COM](/cpp/atl/introduction-to-com).

## -parameters

### -param iid

The interface ID. A pointer to an existing object provided as input.

### -param iface

The returned pointer to the requested COM interface.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

Standard COM method.

## -see-also

[IPreferredRuntimeTypeConcept interface](nn-dbgmodel-ipreferredruntimetypeconcept.md)