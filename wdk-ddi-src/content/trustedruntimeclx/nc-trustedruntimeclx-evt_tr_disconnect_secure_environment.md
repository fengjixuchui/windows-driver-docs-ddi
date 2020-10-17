---
UID: NC:trustedruntimeclx.EVT_TR_DISCONNECT_SECURE_ENVIRONMENT
title: EVT_TR_DISCONNECT_SECURE_ENVIRONMENT (trustedruntimeclx.h)
description: 
ms.assetid: 2b2d799f-56bd-4060-b99e-f7f21f7057c9
ms.date: 10/19/2018
keywords: ["EVT_TR_DISCONNECT_SECURE_ENVIRONMENT callback function"]
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
 - EVT_TR_DISCONNECT_SECURE_ENVIRONMENT
 - trustedruntimeclx/EVT_TR_DISCONNECT_SECURE_ENVIRONMENT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - trustedruntimeclx.h
api_name:
 - EVT_TR_DISCONNECT_SECURE_ENVIRONMENT
---

# EVT_TR_DISCONNECT_SECURE_ENVIRONMENT callback function


## -description

## -parameters

### -param MasterDevice: 

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS values error code. For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -syntax

```cpp
//Declaration

EVT_TR_DISCONNECT_SECURE_ENVIRONMENT EvtTrDisconnectSecureEnvironment; 

// Definition

NTSTATUS EvtTrDisconnectSecureEnvironment 
(
	WDFDEVICE MasterDevice
)
{...}

```

## -remarks

## -see-also