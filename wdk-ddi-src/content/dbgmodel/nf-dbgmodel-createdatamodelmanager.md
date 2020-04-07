---
UID: NF:dbgmodel.CreateDataModelManager
title: CreateDataModelManager function (dbgmodel.h)
description: The initial call a host performs to create and initialize the data model.
ms.assetid: 5694acc5-d39e-408a-8678-88207ca4707a
ms.date: 09/28/2018
keywords: ["CreateDataModelManager function"]
f1_keywords:
 - "dbgmodel/CreateDataModelManager"
ms.keywords: CreateDataModelManager
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
- HeaderDef
api_location: 
- dbgmodel.h
api_name: 
- CreateDataModelManager
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# CreateDataModelManager function


## -description

The initial call a host performs to create and initialize the data model.

## -parameters

### -param debugHost
A pointer to the host interface of the debugger application which is hosting the data model.

### -param manager
The newly created data model manager will be returned here.

## -returns
This function returns HRESULT.

## -remarks
It is unlikely a client will call this function.  Only an application which HOSTS the data model will call this.


## -see-also
[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
