---
UID: NC:trustedruntimeclx.EVT_TR_DESTROY_SECURE_SERVICE_SESSION_CONTEXT
title: EVT_TR_DESTROY_SECURE_SERVICE_SESSION_CONTEXT (trustedruntimeclx.h)
description: 
ms.assetid: 38424b3b-880a-46e6-b4f8-1f364528c0a9
ms.date: 10/19/2018
keywords: ["EVT_TR_DESTROY_SECURE_SERVICE_SESSION_CONTEXT callback function"]
req.header: trustedruntimeclx.h
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
ms.custom: RS5
f1_keywords:
 - EVT_TR_DESTROY_SECURE_SERVICE_SESSION_CONTEXT
 - trustedruntimeclx/EVT_TR_DESTROY_SECURE_SERVICE_SESSION_CONTEXT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - trustedruntimeclx.h
api_name:
 - EVT_TR_DESTROY_SECURE_SERVICE_SESSION_CONTEXT
---

# EVT_TR_DESTROY_SECURE_SERVICE_SESSION_CONTEXT callback function


## -description

## -parameters

### -param ServiceDevice: 

### -param SessionContextObject: 

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS values error code. For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -syntax

```cpp
//Declaration

EVT_TR_DESTROY_SECURE_SERVICE_SESSION_CONTEXT EvtTrDestroySecureServiceSessionContext; 

// Definition

NTSTATUS EvtTrDestroySecureServiceSessionContext 
(
	WDFDEVICE ServiceDevice
	WDFOBJECT * SessionContextObject
)
{...}

```

## -remarks

## -see-also