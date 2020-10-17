---
UID: NN:dbgmodel.IDebugHostModule
title: IDebugHostModule (dbgmodel.h)
description: An (IDebugHostSymbol derived) interface to a particular module.
ms.assetid: 5203121c-1bb5-4c2a-8a3e-6379470e3c26
ms.date: 07/13/2018
keywords: ["IDebugHostModule interface"]
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
 - IDebugHostModule
 - dbgmodel/IDebugHostModule
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostModule
---

# IDebugHostModule interface


## -description

An ([IDebugHostSymbol](nn-dbgmodel-idebughostsymbol.md) derived) interface to a particular module.

## -inheritance

IDebugHostModule interits from [IDebugHostSymbol](nn-dbgmodel-idebughostsymbol.md).

## -remarks

The debugger's notion of a module that is loaded within some address space is represented in two distinct ways in the data model: 

- At the type system level via the IDebugHostModule interface. Here, a module is a symbol and core attributes of the module are interface method calls

- Projected at the data model level via the Debugger.Models.Module data model. This is an extensible encapsulation of the type system IDebugHostModule representation of a module.

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)