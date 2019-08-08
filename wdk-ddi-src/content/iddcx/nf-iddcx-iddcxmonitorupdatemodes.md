---
UID: NF:iddcx.IddCxMonitorUpdateModes
title: IddCxMonitorUpdateModes function (iddcx.h)
description: An OS callback function the driver calls to update the mode list.
old-location: display\iddcxmonitorupdatemodes.htm
tech.root: display
ms.assetid: 0f05931a-2327-454a-9ba7-da02cb2f13d9
ms.date: 05/10/2018
ms.keywords: IddCxMonitorUpdateModes, IddCxMonitorUpdateModes method [Display Devices], display.iddcxmonitorupdatemodes, iddcx/IddCxMonitorUpdateModes
ms.topic: function
f1_keywords:
 - "iddcx/IddCxMonitorUpdateModes"
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
- IddCxMonitorUpdateModes
product:
- Windows
targetos: Windows
req.typenames: 
---

# IddCxMonitorUpdateModes function


## -description




                An OS callback function the driver calls to update the mode list


## -parameters




### -param MonitorObject [in]

The monitor object being updated


### -param pInArgs [in]

Input arguments of function 


## -returns




(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.
                    



