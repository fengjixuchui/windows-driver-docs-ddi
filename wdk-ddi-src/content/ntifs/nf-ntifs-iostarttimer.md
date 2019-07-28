---
UID: NF:ntifs.IoStartTimer
title: IoStartTimer function (ntifs.h)
description: The IoStartTimer routine enables the timer associated with a given device object so the driver-supplied IoTimer routine is called once per second.
old-location: kernel\iostarttimer.htm
tech.root: kernel
ms.assetid: 2e13d7da-7ef3-4c2e-b028-f7d37548c208
ms.date: 04/30/2018
ms.keywords: IoStartTimer, IoStartTimer routine [Kernel-Mode Driver Architecture], k104_bca7aa97-41e1-48e4-96df-52dd6109cd51.xml, kernel.iostarttimer, wdm/IoStartTimer
ms.topic: function
f1_keywords:
 - "ntifs/IoStartTimer"
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoStartTimer
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoStartTimer function


## -description


The <b>IoStartTimer</b> routine enables the timer associated with a given device object so the driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-io_timer_routine">IoTimer</a> routine is called once per second.


## -parameters




### -param DeviceObject [in]

Pointer to a device object whose timer routine is to be called.


## -returns



None




## -remarks



The driver must already have set up the IoTimer routine for the <i>DeviceObject</i> by calling <b>IoInitializeTimer</b>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioinitializetimer">IoInitializeTimer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-iostoptimer">IoStopTimer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-io_timer_routine">IoTimer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keinitializedpc">KeInitializeDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keinitializetimer">KeInitializeTimer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kesettimer">KeSetTimer</a>
 

 

