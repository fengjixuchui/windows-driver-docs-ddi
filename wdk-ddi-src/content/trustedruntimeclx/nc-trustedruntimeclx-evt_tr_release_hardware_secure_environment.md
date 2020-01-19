---
UID: NC:trustedruntimeclx.EVT_TR_RELEASE_HARDWARE_SECURE_ENVIRONMENT
title: EVT_TR_RELEASE_HARDWARE_SECURE_ENVIRONMENT (trustedruntimeclx.h)
description: 
ms.assetid: 9ac67112-a870-4aa9-a676-fabb0cf36cf3
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "trustedruntimeclx/EVT_TR_RELEASE_HARDWARE_SECURE_ENVIRONMENT"
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
topic_type: 
- apiref
api_type: 
- UserDefined
api_location: 
- trustedruntimeclx.h
api_name: 
- EVT_TR_RELEASE_HARDWARE_SECURE_ENVIRONMENT
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# EVT_TR_RELEASE_HARDWARE_SECURE_ENVIRONMENT callback function

## -description

 

## -syntax

```cpp
//Declaration

EVT_TR_RELEASE_HARDWARE_SECURE_ENVIRONMENT EvtTrReleaseHardwareSecureEnvironment; 

// Definition

NTSTATUS EvtTrReleaseHardwareSecureEnvironment 
(
	WDFDEVICE MasterDevice
	WDFCMRESLIST TranslatedResources
)
{...}

```

## -parameters

### -param MasterDevice: 
### -param TranslatedResources: 



## -returns


Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks




## -see-also
