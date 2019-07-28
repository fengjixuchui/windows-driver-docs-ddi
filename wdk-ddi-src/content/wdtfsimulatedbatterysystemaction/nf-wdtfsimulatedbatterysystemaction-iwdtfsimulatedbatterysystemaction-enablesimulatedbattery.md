---
UID: NF:wdtfsimulatedbatterysystemaction.IWDTFSimulatedBatterySystemAction.EnableSimulatedBattery
title: IWDTFSimulatedBatterySystemAction::EnableSimulatedBattery (wdtfsimulatedbatterysystemaction.h)
description: Enables the simulated battery.
old-location: dtf\iwdtfsimulatedbatterysystemaction_enablesimulatedbattery.htm
tech.root: dtf
ms.assetid: c9ca8bb4-2a05-4934-b589-41fba8092b1b
ms.date: 04/04/2018
ms.keywords: EnableSimulatedBattery, EnableSimulatedBattery method [Windows Device Testing Framework], EnableSimulatedBattery method [Windows Device Testing Framework],IWDTFSimulatedBatterySystemAction interface, IWDTFSimulatedBatterySystemAction interface [Windows Device Testing Framework],EnableSimulatedBattery method, IWDTFSimulatedBatterySystemAction.EnableSimulatedBattery, IWDTFSimulatedBatterySystemAction::EnableSimulatedBattery, dtf.iwdtfsimulatedbatterysystemaction_enablesimulatedbattery, wdtfsimulatedbatterysystemaction/IWDTFSimulatedBatterySystemAction::EnableSimulatedBattery
ms.topic: method
f1_keywords:
 - "wdtfsimulatedbatterysystemaction/IWDTFSimulatedBatterySystemAction.EnableSimulatedBattery"
req.header: wdtfsimulatedbatterysystemaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFSimulatedBatterySystemAction.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- wdtfsimulatedbatterysystemaction.h
api_name:
- IWDTFSimulatedBatterySystemAction.EnableSimulatedBattery
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFSimulatedBatterySystemAction::EnableSimulatedBattery


## -description



Enables the simulated battery.



 Use this method to enable the simulated battery (installs simulated
    battery device).  This does not guarantee the ability to simulate DC by
    itself, the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">IWDTFSimulatedBatterySystemAction::DisableRealBatteries</a> method must also be called in order to guarantee a real battery doesn't interfere with the simulation.


## -parameters




### -param pbSuccess [out, retval]


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">IWDTFSimulatedBatterySystemAction</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">IWDTFSimulatedBatterySystemAction::DisableRealBatteries</a>
 

 

