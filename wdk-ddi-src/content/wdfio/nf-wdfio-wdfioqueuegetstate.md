---
UID: NF:wdfio.WdfIoQueueGetState
title: WdfIoQueueGetState function (wdfio.h)
description: The WdfIoQueueGetState method returns the status of a specified I/O queue.
old-location: wdf\wdfioqueuegetstate.htm
tech.root: wdf
ms.assetid: 83bfddd5-fc4d-4f5c-9904-7564810f5b4c
ms.date: 02/26/2018
keywords: ["WdfIoQueueGetState function"]
ms.keywords: DFQueueObjectRef_756666e1-e5eb-4bcc-907e-65b10e580396.xml, WdfIoQueueGetState, WdfIoQueueGetState method, kmdf.wdfioqueuegetstate, wdf.wdfioqueuegetstate, wdfio/WdfIoQueueGetState
f1_keywords:
 - "wdfio/WdfIoQueueGetState"
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfIoQueueGetState
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoQueueGetState function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfIoQueueGetState</b> method returns the status of a specified I/O queue.


## -parameters




### -param Queue [in]

A handle to a framework queue object.


### -param QueueRequests [out, optional]

A pointer to a location that receives the number of I/O requests that are currently in the I/O queue and have not been delivered to the driver. This pointer is optional and can be <b>NULL</b>.


### -param DriverRequests [out, optional]

A pointer to a location that receives the number of I/O requests that have been delivered to the driver but that the driver has not completed or canceled. This pointer is optional and can be <b>NULL</b>.


## -returns



<b>WdfIoQueueGetState</b> returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ne-wdfio-_wdf_io_queue_state">WDF_IO_QUEUE_STATE</a>-typed value, which can contain the bitwise OR of several <b>WDF_IO_QUEUE_STATE</b> enumerators. 

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



After calling <b>WdfIoQueueGetState</b>, your driver can pass the received state value to the following functions, which are defined in <i>Wdfio.h</i>:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_drained">WDF_IO_QUEUE_DRAINED</a>, which returns <b>TRUE</b> if the queue is drained.

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_idle">WDF_IO_QUEUE_IDLE</a>, which returns <b>TRUE</b> if the queue is idle.

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_purged">WDF_IO_QUEUE_PURGED</a>, which returns <b>TRUE</b> if the queue is purged.

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_ready">WDF_IO_QUEUE_READY</a>, which returns <b>TRUE</b> if the queue is ready.

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_stopped">WDF_IO_QUEUE_STOPPED</a>, which returns <b>TRUE</b> if the queue is stopped.

</li>
</ul>
If your driver uses the framework's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-automatic-synchronization">automatic synchronization</a>, the I/O queue's status will not change between the time that the <b>WdfIoQueueGetState</b> method obtains status information from the framework and the time that the method returns. Otherwise the queue's status might change before the <b>WdfIoQueueGetState</b> method returns.

For more information about the <b>WdfIoQueueGetState</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/managing-i-o-queues">Obtaining I/O Queue Properties</a>.


#### Examples

The following code example is a routine that returns <b>TRUE</b> if a specified I/O queue is idle.

```cpp
BOOLEAN
IsQueueIdle(
    IN WDFQUEUE Queue
    )
{
    WDF_IO_QUEUE_STATE queueStatus;
    queueStatus = WdfIoQueueGetState(
                                     Queue,
                                     NULL,
                                     NULL
                                     );
    return (WDF_IO_QUEUE_IDLE(queueStatus)) ? TRUE : FALSE;
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_state">EvtIoQueueState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ne-wdfio-_wdf_io_queue_state">WDF_IO_QUEUE_STATE</a>
 

 

