---
UID: NN:dbgmodel.IHostDataModelAccess
title: IHostDataModelAccess (dbgmodel.h)
description: IHostDataModelAccess is the bridge interface between the legacy IDebug* interfaces of Debugging Tools for Windows and the data model. 
ms.assetid: 00f72d8d-6a79-4000-b68d-05ba984585f6
ms.date: 07/16/2018
keywords: ["IHostDataModelAccess interface"]
f1_keywords:
 - "dbgmodel/IHostDataModelAccess"
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
topic_type: 
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IHostDataModelAccess
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IHostDataModelAccess interface

## -description

When DebugExtensionInitialize is called, it creates a debug client and gets access to the data model. Such access is provided by a bridge interface between the legacy IDebug* interfaces of Debugging Tools for Windows and the data model. This bridge interface is IHostDataModelAccess. 


## -inheritance
IHostDataModelAccess interits from IUnknown. 
## -remarks

An interface *suggested* on the per-host extensibility mechanism to get from the host extensibility mechanism to the model based one.  Extensions which are written to a host-specific API set can query this mechanism to get to the data model and create host-agnostic extensions.

As an example, DbgEng based extensions can query for this interface from any IDebug* (Client/Control/etc...) interface to get to the model and access model APIs.  Such extensions are hybrid (they are still specific to a particular host but contain portions that may be factored out later for a general model based extension).

This is the **ONLY** interface in this set of APIs which is not intended to be host agnostic.

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
