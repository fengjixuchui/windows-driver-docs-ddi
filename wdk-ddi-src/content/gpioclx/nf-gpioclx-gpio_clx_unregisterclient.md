---
UID: NF:gpioclx.GPIO_CLX_UnregisterClient
title: GPIO_CLX_UnregisterClient function (gpioclx.h)
description: The GPIO_CLX_UnregisterClient method removes a general-purpose I/O (GPIO) controller driver's registration with the GPIO framework extension (GpioClx).
old-location: gpio\gpio_clx_unregisterclient.htm
tech.root: GPIO
ms.assetid: 2ECBF3D9-F613-4829-B2E0-FF5E21A596EC
ms.date: 02/15/2018
ms.keywords: GPIO.gpio_clx_unregisterclient, GPIO_CLX_UnregisterClient, GPIO_CLX_UnregisterClient method [Parallel Ports], gpioclx/GPIO_CLX_UnregisterClient
ms.topic: function
f1_keywords:
 - "gpioclx/GPIO_CLX_UnregisterClient"
req.header: gpioclx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: Msgpioclxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Msgpioclxstub.lib
- Msgpioclxstub.dll
api_name:
- GPIO_CLX_UnregisterClient
product:
- Windows
targetos: Windows
req.typenames: 
---

# GPIO_CLX_UnregisterClient function


## -description


The <b>GPIO_CLX_UnregisterClient</b> method removes a general-purpose I/O (GPIO) controller driver's registration with the GPIO framework extension (GpioClx).


## -parameters




### -param Driver [in]

A WDFDRIVER handle to the framework driver object for the GPIO controller driver.


## -returns



<b>GPIO_CLX_UnregisterClient</b> returns STATUS_SUCCESS if the call is successful. Possible return values include the following error code.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The caller is not a registered client of GpioClx.

</td>
</tr>
</table>
 




## -remarks



A GPIO controller driver calls this method to cancel its registration. The driver registered in a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/gpioclx/nf-gpioclx-gpio_clx_registerclient">GPIO_CLX_RegisterClient</a> method.

Typically, the GPIO controller driver calls this method from its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdriver/nc-wdfdriver-evt_wdf_driver_unload">EvtDriverUnload</a> event callback function, which runs shortly before the driver unloads.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdriver/nc-wdfdriver-evt_wdf_driver_unload">EvtDriverUnload</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/gpioclx/nf-gpioclx-gpio_clx_registerclient">GPIO_CLX_RegisterClient</a>
 

 

