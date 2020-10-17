---
UID: NN:dbgmodel.IStringDisplayableConcept
title: IStringDisplayableConcept (dbgmodel.h)
description: Interface which clients must implement on any object which is convertible to a display string.
ms.assetid: 108b4841-40cd-4771-ac66-953c9910b143
ms.date: 10/05/2018
keywords: ["IStringDisplayableConcept interface"]
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
 - IStringDisplayableConcept
 - dbgmodel/IStringDisplayableConcept
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IStringDisplayableConcept
---

# IStringDisplayableConcept interface


## -description

Interface which clients must implement on any object which is convertible to a display string.

Clients should not rely on the form of this string conversion for programmatic purposes.  It is intended for display purposes only.

## -inheritance

IStringDisplayableConcept interits from IUnknown.

## -remarks

An object which wishes to provide a string conversion for display purposes can implement the string displayable concept through implementation of the IStringDisplayableConcept interface.

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)