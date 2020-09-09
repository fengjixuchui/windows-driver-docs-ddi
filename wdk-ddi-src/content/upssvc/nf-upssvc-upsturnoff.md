---
UID: NF:upssvc.UPSTurnOff
title: UPSTurnOff function (upssvc.h)
description: The UPSTurnOff function turns off the UPS unit's power outlets, after a specified delay time.
old-location: battery\upsturnoff.htm
tech.root: battery
ms.assetid: 17ae946a-e57e-48bd-9213-cf47db2cba64
ms.date: 02/15/2018
keywords: ["UPSTurnOff function"]
ms.keywords: UPSTurnOff, UPSTurnOff function [Battery Devices], UPS_fns_ab585909-7eee-470f-b33f-6045f839ceed.xml, battery.upsturnoff, upssvc/UPSTurnOff
req.header: upssvc.h
req.include-header: Upssvc.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - UPSTurnOff
 - upssvc/UPSTurnOff
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - upssvc.h
api_name:
 - UPSTurnOff
---

# UPSTurnOff function


## -description

The <b>UPSTurnOff</b> function turns off the UPS unit's power outlets, after a specified delay time.

## -parameters

### -param aTurnOffDelay 

[in]
Specifies the minimum amount of time, in seconds, to wait before turning off the UPS unit's power outlets.

## -remarks

The actual delay time should not be less than that specified by <i>aTurnOffDelay</i>, to ensure adequate time for the operating system to shut down. 

The default value for <i>aTurnOffDelay</i> is 180 seconds.

The function must not postpone the request to turn off the power. Doing so could result in the operating system unloading the UPS service and the UPS minidriver.

On the other hand, the function must not turn off power from a UPS system that does not have an internal turnoff delay. Doing so will result in a premature loss of power to the computer, which can cause system corruption.

