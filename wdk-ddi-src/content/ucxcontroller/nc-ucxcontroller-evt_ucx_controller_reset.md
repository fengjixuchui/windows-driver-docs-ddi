---
UID: NC:ucxcontroller.EVT_UCX_CONTROLLER_RESET
title: EVT_UCX_CONTROLLER_RESET (ucxcontroller.h)
description: The client driver's implementation that UCX calls to reset the controller.
old-location: buses\evt_ucx_controller_reset.htm
tech.root: usbref
ms.assetid: 8c01d677-5ce4-44f6-8342-2152e851de87
ms.date: 05/07/2018
keywords: ["EVT_UCX_CONTROLLER_RESET callback function"]
ms.keywords: EVT_UCX_CONTROLLER_RESET, EVT_UCX_CONTROLLER_RESET callback, EvtUcxControllerReset, EvtUcxControllerReset callback function [Buses], PEVT_UCX_CONTROLLER_RESET, PEVT_UCX_CONTROLLER_RESET callback function pointer [Buses], buses.evt_ucx_controller_reset, ucxcontroller/EvtUcxControllerReset
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_UCX_CONTROLLER_RESET
 - ucxcontroller/EVT_UCX_CONTROLLER_RESET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ucxcontroller.h
api_name:
 - PEVT_UCX_CONTROLLER_RESET
---

# EVT_UCX_CONTROLLER_RESET callback function


## -description

The client driver's implementation that UCX calls to reset the controller.

## -parameters

### -param UcxController 

[in]
 A handle to the UCX controller that the client driver received in a previous call to  the <a href="/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a> method.

## -remarks

The UCX client driver registers its <i>EVT_UCX_CONTROLLER_RESET</i> implementation with the USB host controller extension (UCX) by calling the <a href="/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a> method.

The client driver indicates completion of this event by calling the <a href="/windows-hardware/drivers/ddi/ucxcontroller/nf-ucxcontroller-ucxcontrollerresetcomplete">UcxControllerResetComplete</a> method. Doing so ensures that UCX does not call <i>EVT_UCX_CONTROLLER_RESET</i> a second time before this event callback completes.

If the client driver calls <a href="/windows-hardware/drivers/ddi/ucxcontroller/nf-ucxcontroller-ucxcontrollerneedsreset">UcxControllerNeedsReset</a>, UCX calls this event callback function.  However, UCX may call this event callback function even when the client driver has not called <b>UcxControllerNeedsReset</b>. 


#### Examples


```
VOID
Controller_EvtControllerReset(
    UCXCONTROLLER UcxController
)

{
    UCX_CONTROLLER_RESET_COMPLETE_INFO controllerResetCompleteInfo;

    //
    // TODO: Reset the controller
    //

    //
    // TODO: Were devices and endpoints programmed in the controller before the reset
    // still programmed in the controller after the reset?
    //
    UCX_CONTROLLER_RESET_COMPLETE_INFO_INIT(&controllerResetCompleteInfo,
                                            UcxControllerStateLost,
                                            TRUE); // reset due to UCX, received EvtReset after WDF power-up

    DbgTrace(TL_INFO, Controller, "Controller_EvtControllerReset");

    UcxControllerResetComplete(UcxController, &controllerResetCompleteInfo);
}
```


## -see-also

<a href="/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a>



<a href="/windows-hardware/drivers/ddi/ucxcontroller/nf-ucxcontroller-ucxcontrollerneedsreset">UcxControllerNeedsReset</a>



<a href="/windows-hardware/drivers/ddi/ucxcontroller/nf-ucxcontroller-ucxcontrollerresetcomplete">UcxControllerResetComplete</a>