---
UID: NF:wdfio.WDF_IO_QUEUE_STOPPED
title: WDF_IO_QUEUE_STOPPED function (wdfio.h)
description: The WDF_IO_QUEUE_STOPPED function returns TRUE if an I/O queue's state indicates that the queue is stopped.
old-location: wdf\wdf_io_queue_stopped.htm
tech.root: wdf
ms.assetid: 8257c636-824d-4909-b0cb-76d72ac980fa
ms.date: 02/26/2018
keywords: ["WDF_IO_QUEUE_STOPPED function"]
ms.keywords: DFQueueObjectRef_55457efd-0074-4be5-b078-bb223963bfca.xml, WDF_IO_QUEUE_STOPPED, WDF_IO_QUEUE_STOPPED function, kmdf.wdf_io_queue_stopped, wdf.wdf_io_queue_stopped, wdfio/WDF_IO_QUEUE_STOPPED
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: None
req.dll: 
req.irql: Any IRQL.
targetos: Windows
req.typenames: 
f1_keywords:
 - WDF_IO_QUEUE_STOPPED
 - wdfio/WDF_IO_QUEUE_STOPPED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - None
 - None.dll
api_name:
 - WDF_IO_QUEUE_STOPPED
---

# WDF_IO_QUEUE_STOPPED function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_IO_QUEUE_STOPPED</b> function returns <b>TRUE</b> if an I/O queue's state indicates that the queue is stopped.

## -parameters

### -param State 

[in]
A <a href="/windows-hardware/drivers/ddi/wdfio/ne-wdfio-_wdf_io_queue_state">WDF_IO_QUEUE_STATE</a>-typed value that <a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuegetstate">WdfIoQueueGetState</a> returns.

## -returns

<b>WDF_IO_QUEUE_STOPPED</b> returns <b>TRUE</b> if the specified queue state indicates that the queue is stopped. Otherwise, the function returns <b>FALSE</b>.

## -remarks

An I/O queue is stopped if it can accept new I/O requests but the framework is not delivering them to the driver. 

Your driver can call <b>WDF_IO_QUEUE_STOPPED</b> after it has called <a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuegetstate">WdfIoQueueGetState</a>.

For more information about I/O queue states, see <a href="/windows-hardware/drivers/ddi/wdfio/ne-wdfio-_wdf_io_queue_state">WDF_IO_QUEUE_STATE</a>.


#### Examples

The following code example is a routine that returns <b>TRUE</b> if a specified I/O queue is stopped.

```cpp
BOOLEAN
IsQueueStopped(
    IN WDFQUEUE Queue
    )
{
    WDF_IO_QUEUE_STATE queueStatus;
    queueStatus = WdfIoQueueGetState(
                                     Queue,
                                     NULL,
                                     NULL
                                     );
    return (WDF_IO_QUEUE_STOPPED(queueStatus)) ? TRUE : FALSE;
}
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_drained">WDF_IO_QUEUE_DRAINED</a>



<a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_idle">WDF_IO_QUEUE_IDLE</a>



<a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_purged">WDF_IO_QUEUE_PURGED</a>



<a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_ready">WDF_IO_QUEUE_READY</a>