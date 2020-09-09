---
UID: NC:ufxproprietarycharger.UFX_PROPRIETARY_CHARGER_ABORT_OPERATION
title: UFX_PROPRIETARY_CHARGER_ABORT_OPERATION (ufxproprietarycharger.h)
description: The filter driver's implementation to abort a charger operation.
old-location: buses\ufx_proprietary_charger_abort_operation.htm
tech.root: usbref
ms.assetid: 32BCBE1C-BD0E-46D6-9C6D-6B8F1CE0E540
ms.date: 05/07/2018
keywords: ["UFX_PROPRIETARY_CHARGER_ABORT_OPERATION callback function"]
ms.keywords: PFN_UFX_PROPRIETARY_CHARGER_ABORT_OPERATION, PFN_UFX_PROPRIETARY_CHARGER_ABORT_OPERATION callback function pointer [Buses], UFX_PROPRIETARY_CHARGER_ABORT_OPERATION, UFX_PROPRIETARY_CHARGER_ABORT_OPERATION callback, UfxProprietaryChargerAbort, UfxProprietaryChargerAbort callback function [Buses], buses.ufx_proprietary_charger_abort_operation, ufxproprietarycharger/UfxProprietaryChargerAbort
req.header: ufxproprietarycharger.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - UFX_PROPRIETARY_CHARGER_ABORT_OPERATION
 - ufxproprietarycharger/UFX_PROPRIETARY_CHARGER_ABORT_OPERATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ufxproprietarycharger.h
api_name:
 - PFN_UFX_PROPRIETARY_CHARGER_ABORT_OPERATION
---

# UFX_PROPRIETARY_CHARGER_ABORT_OPERATION callback function


## -description

The filter driver's implementation to abort a charger operation.

## -parameters

### -param Context 

[in]
    A pointer to a driver-defined context.

## -returns

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.

## -remarks

To support handling of proprietary chargers, the USB lower filter driver must publish support. During the publishing process, the driver also registers its implementation of this  callback function. For more information, see <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188012(v=vs.85)">USB filter driver for supporting proprietary chargers</a>.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188012(v=vs.85)">USB filter driver for supporting proprietary chargers</a>

