---
UID: NF:ntddk.KeSetTargetProcessorDpc
title: KeSetTargetProcessorDpc function (ntddk.h)
description: The KeSetTargetProcessorDpc routine specifies the processor that a DPC routine will be run on.
old-location: kernel\kesettargetprocessordpc.htm
tech.root: kernel
ms.assetid: 9fd86250-a495-4628-a07b-f5c44df69c0e
ms.date: 04/30/2018
ms.keywords: KeSetTargetProcessorDpc, KeSetTargetProcessorDpc routine [Kernel-Mode Driver Architecture], k105_a7931e50-ba41-47a0-9056-e9479ac46808.xml, kernel.kesettargetprocessordpc, wdm/KeSetTargetProcessorDpc
ms.topic: function
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeSetTargetProcessorDpc
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeSetTargetProcessorDpc function


## -description


The <b>KeSetTargetProcessorDpc</b> routine specifies the processor that a DPC routine will be run on.


## -parameters




### -param Dpc [in, out]

Pointer to the caller's DPC object, which <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keinitializedpc">KeInitializeDpc</a> already initialized.


### -param Number [in]

Specifies the zero-based number of the target processor on which the DPC should be queued and executed.


## -returns



None




## -remarks



On multiprocessor systems, each processor has its own DPC queue. The <b>KeSetTargetProcessorDpc</b> routine specifies which processor's queue the system should use when the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keinsertqueuedpc">KeInsertQueueDpc</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iorequestdpc">IoRequestDpc</a> to queue a DPC to be run later.

Starting with Windows Vista, you can also use <b>KeSetTargetProcessorDpc</b> to specify the target processor for <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/threaded-dpcs">threaded DPCs</a>.

A call to <b>KeSetTargetProcessorDpcEx</b> that occurs after a DPC object has been queued has no effect on the selection of a processor for the DPC routine to run on. To control the selection of the target processor, a <b>KeSetTargetProcessorDpc</b> call must occur before the call to <b>KeInsertQueueDpc</b> or <b>IoRequestDpc</b> that queues the DPC object.

For more information about DPC queues, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/organization-of-dpc-queues">Organization of DPC Queues</a>.

Windows 7 and later versions of Windows support processor groups. Drivers that are designed to handle information about processor groups should use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kesettargetprocessordpcex">KeSetTargetProcessorDpcEx</a> routine, which specifies a processor group, instead of <b>KeSetTargetProcessorDpc</b>, which does not. However, the implementation of <b>KeSetTargetProcessorDpc</b> in Windows 7 and later versions of Windows provides compatibility for drivers that were written for earlier versions of Windows, which do not support processor groups. In this implementation, if <i>Number</i> is less than the number of active logical processors in group 0, <b>KeSetTargetProcessorDpc</b> sets the target for the DPC to the processor in group 0 that is specified by <i>Number</i>. Otherwise, the DPC target does not change.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iorequestdpc">IoRequestDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-kegetcurrentprocessornumber">KeGetCurrentProcessorNumber</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keinitializedpc">KeInitializeDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keinsertqueuedpc">KeInsertQueueDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-kesetimportancedpc">KeSetImportanceDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kesettargetprocessordpcex">KeSetTargetProcessorDpcEx</a>
 

 

