---
UID: NC:trustedruntimeclx.EVT_TR_PROCESS_OTHER_SECURE_SERVICE_IO
title: EVT_TR_PROCESS_OTHER_SECURE_SERVICE_IO (trustedruntimeclx.h)
description: 
ms.assetid: 73774bab-6134-40b9-97f7-5ee28aa0929f
ms.date: 10/19/2018
keywords: ["EVT_TR_PROCESS_OTHER_SECURE_SERVICE_IO callback function"]
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
 - EVT_TR_PROCESS_OTHER_SECURE_SERVICE_IO
 - trustedruntimeclx/EVT_TR_PROCESS_OTHER_SECURE_SERVICE_IO
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - trustedruntimeclx.h
api_name:
 - EVT_TR_PROCESS_OTHER_SECURE_SERVICE_IO
---

# EVT_TR_PROCESS_OTHER_SECURE_SERVICE_IO callback function


## -description

## -parameters

### -param ServiceDevice: 

### -param SessionContext: 

### -param Request: 

## -syntax

```cpp
//Declaration

EVT_TR_PROCESS_OTHER_SECURE_SERVICE_IO EvtTrProcessOtherSecureServiceIo; 

// Definition

VOID EvtTrProcessOtherSecureServiceIo 
(
	WDFDEVICE ServiceDevice
	WDFOBJECT SessionContext
	WDFREQUEST Request
)
{...}

```

## -remarks

## -see-also

