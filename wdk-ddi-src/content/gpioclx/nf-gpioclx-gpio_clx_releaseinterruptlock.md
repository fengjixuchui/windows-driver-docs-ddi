---
UID: NF:gpioclx.GPIO_CLX_ReleaseInterruptLock
title: GPIO_CLX_ReleaseInterruptLock function (gpioclx.h)
description: The GPIO_CLX_ReleaseInterruptLock method releases an interrupt lock on the specified bank.
old-location: gpio\gpio_clx_releaseinterruptlock.htm
tech.root: GPIO
ms.assetid: 195B9FA2-F7B2-4EA0-9D53-63E438666760
ms.date: 02/15/2018
keywords: ["GPIO_CLX_ReleaseInterruptLock function"]
ms.keywords: GPIO.gpio_clx_releaseinterruptlock, GPIO_CLX_ReleaseInterruptLock, GPIO_CLX_ReleaseInterruptLock method [Parallel Ports], gpioclx/GPIO_CLX_ReleaseInterruptLock
f1_keywords:
 - "gpioclx/GPIO_CLX_ReleaseInterruptLock"
 - "GPIO_CLX_ReleaseInterruptLock"
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
req.irql: See Remarks.
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Msgpioclxstub.lib
- Msgpioclxstub.dll
api_name:
- GPIO_CLX_ReleaseInterruptLock
targetos: Windows
req.typenames: 
---

# GPIO_CLX_ReleaseInterruptLock function


## -description


The <b>GPIO_CLX_ReleaseInterruptLock</b> method releases an interrupt lock on the specified bank.


## -parameters




### -param Context [in]

A pointer to the GPIO controller driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/gpio/gpio-device-contexts">device context</a>. The GPIO framework extension (GpioClx) passes this pointer value as a parameter to the callback functions that are implemented by the GPIO controller driver.


### -param BankId [in]

The identifier for this bank of GPIO pins. If N is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to N–1.


## -remarks



This method releases the interrupt lock that the caller acquired in a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_acquireinterruptlock">GPIO_CLX_AcquireInterruptLock</a> method.

If the previous call to the <b>GPIO_CLX_AcquireInterruptLock</b> method raised the calling thread's IRQL, <b>GPIO_CLX_ReleaseInterruptLock</b> restores this IRQL to its original level.

If the <i>Context</i> parameter is NULL or points to an invalid GPIO device context, this method causes a bug check in debug builds of GpioClx.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_acquireinterruptlock">GPIO_CLX_AcquireInterruptLock</a>
 

 

