---
UID: NF:iddcx.IddCxMonitorCreate
title: IddCxMonitorCreate function (iddcx.h)
description: An OS callback function the driver calls to create a monitor object that can later be used for arrival.
old-location: display\iddcxmonitorcreate.htm
tech.root: display
ms.assetid: 2e089827-dd50-43cb-9e1a-34c439780831
ms.date: 05/10/2018
keywords: ["IddCxMonitorCreate function"]
ms.keywords: IddCxMonitorCreate, IddCxMonitorCreate method [Display Devices], display.iddcxmonitorcreate, iddcx/IddCxMonitorCreate
f1_keywords:
 - "iddcx/IddCxMonitorCreate"
 - "IddCxMonitorCreate"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- IddCx.dll
api_name:
- IddCxMonitorCreate
targetos: Windows
req.typenames: 
---

# IddCxMonitorCreate function


## -description


An OS callback function the driver calls to create a monitor object that can later be used for arrival.

                


## -parameters




### -param AdapterObject [in]

The adapter object that is hosting the newly arrived monitor


### -param pInArgs [in]

Input arguments to the function


### -param pOutArgs [out]

Output arguments to the function


## -returns




(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.
                    



