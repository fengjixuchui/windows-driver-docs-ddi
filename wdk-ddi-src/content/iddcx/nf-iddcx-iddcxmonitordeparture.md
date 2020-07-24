---
UID: NF:iddcx.IddCxMonitorDeparture
title: IddCxMonitorDeparture function (iddcx.h)
description: An OS callback function the driver calls to report a monitor departure from the WDDM graphics adapter.
old-location: display\iddcxmonitordeparture.htm
tech.root: display
ms.assetid: d23f70ee-a58d-4db1-8f21-b27887d661b9
ms.date: 05/10/2018
keywords: ["IddCxMonitorDeparture function"]
ms.keywords: IddCxMonitorDeparture, IddCxMonitorDeparture method [Display Devices], display.iddcxmonitordeparture, iddcx/IddCxMonitorDeparture
f1_keywords:
 - "iddcx/IddCxMonitorDeparture"
 - "IddCxMonitorDeparture"
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: IddCxStub.lib 
req.dll: IddCx.dll 
req.irql: _Must_inspect_result_
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- IddCx.dll
api_name:
- IddCxMonitorDeparture
targetos: Windows
req.typenames: 
---

# IddCxMonitorDeparture function


## -description




                An OS callback function the driver calls to report a monitor departure from the WDDM graphics adapter


## -parameters




### -param MonitorObject [in]

The monitor object that is departing


## -returns




(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.
                    



