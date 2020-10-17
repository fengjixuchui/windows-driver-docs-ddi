---
UID: NS:wdfio._WDF_IO_QUEUE_CONFIG
title: _WDF_IO_QUEUE_CONFIG (wdfio.h)
description: The WDF_IO_QUEUE_CONFIG structure contains configuration information for a framework queue object.
old-location: wdf\wdf_io_queue_config.htm
tech.root: wdf
ms.assetid: aa8b64a7-eae9-444c-892f-841ca5a610cf
ms.date: 02/26/2018
keywords: ["WDF_IO_QUEUE_CONFIG structure"]
ms.keywords: "*PWDF_IO_QUEUE_CONFIG, DFQueueObjectRef_5fda62f6-b76d-4691-9354-e091af8a5567.xml, PWDF_IO_QUEUE_CONFIG, PWDF_IO_QUEUE_CONFIG structure pointer, WDF_IO_QUEUE_CONFIG, WDF_IO_QUEUE_CONFIG structure, _WDF_IO_QUEUE_CONFIG, kmdf.wdf_io_queue_config, wdf.wdf_io_queue_config, wdfio/PWDF_IO_QUEUE_CONFIG, wdfio/WDF_IO_QUEUE_CONFIG"
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
req.typenames: WDF_IO_QUEUE_CONFIG, *PWDF_IO_QUEUE_CONFIG
f1_keywords:
 - _WDF_IO_QUEUE_CONFIG
 - wdfio/_WDF_IO_QUEUE_CONFIG
 - PWDF_IO_QUEUE_CONFIG
 - wdfio/PWDF_IO_QUEUE_CONFIG
 - WDF_IO_QUEUE_CONFIG
 - wdfio/WDF_IO_QUEUE_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfio.h
api_name:
 - WDF_IO_QUEUE_CONFIG
---

# _WDF_IO_QUEUE_CONFIG structure


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_IO_QUEUE_CONFIG</b> structure contains configuration information for a framework queue object.

## -struct-fields

### -field Size

The length, in bytes, of this structure.

### -field DispatchType

A <a href="/windows-hardware/drivers/ddi/wdfio/ne-wdfio-_wdf_io_queue_dispatch_type">WDF_IO_QUEUE_DISPATCH_TYPE</a> enumerator that identifies the request dispatching type for the queue.

### -field PowerManaged

A <a href="/windows-hardware/drivers/ddi/wdftypes/ne-wdftypes-_wdf_tri_state">WDF_TRI_STATE</a>-typed value that, if set to <b>WdfTrue</b>, indicates that the framework handles power management of the queue. 

If set to <b>WdfFalse</b>, the driver must handle power management of the queue. 

If set to <b>WdfUseDefault</b>, the framework handles power management for the queue unless the driver calls <a href="/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitsetfilter">WdfFdoInitSetFilter</a>. 

Drivers above the <a href="/windows-hardware/drivers/wdf/power-policy-ownership">power policy owner</a> in the driver stack must not set the <b>PowerManaged</b> member to <b>WdfTrue</b>. 

For more information about power-managed I/O queues, see <a href="/windows-hardware/drivers/wdf/power-management-for-i-o-queues">Power Management for I/O Queues</a>.

### -field AllowZeroLengthRequests

A Boolean value that, if <b>TRUE</b>, indicates that the driver expects to receive read or write requests that have a buffer length of zero, so the framework delivers these requests to the driver. If <b>FALSE</b>, the framework does not deliver these requests to the driver; instead, it completes them with a completion status of STATUS_SUCCESS.

### -field DefaultQueue

A Boolean value that, if <b>TRUE</b>, indicates that the queue will be the device's <a href="/windows-hardware/drivers/wdf/creating-i-o-queues">default I/O queue</a>. If <b>FALSE</b>, the queue will not be the device's default queue.

### -field EvtIoDefault

A pointer to the driver's queue-specific <a href="/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_default">EvtIoDefault</a> callback function, or <b>NULL</b>.

### -field EvtIoRead

A pointer to the driver's queue-specific <a href="/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_read">EvtIoRead</a> callback function, or <b>NULL</b>.

### -field EvtIoWrite

A pointer to the driver's queue-specific <a href="/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_write">EvtIoWrite</a> callback function, or <b>NULL</b>.

### -field EvtIoDeviceControl

A pointer to the driver's queue-specific <a href="/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_device_control">EvtIoDeviceControl</a> callback function, or <b>NULL</b>.

### -field EvtIoInternalDeviceControl

A pointer to the driver's queue-specific <a href="/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_internal_device_control">EvtIoInternalDeviceControl</a> callback function, or <b>NULL</b>.

### -field EvtIoStop

A pointer to the driver's queue-specific <a href="/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_stop">EvtIoStop</a> callback function, or <b>NULL</b>.

### -field EvtIoResume

A pointer to the driver's queue-specific <a href="/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_resume">EvtIoResume</a> callback function, or <b>NULL</b>.

### -field EvtIoCanceledOnQueue

A pointer to the driver's queue-specific <a href="/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_canceled_on_queue">EvtIoCanceledOnQueue</a> callback function, or <b>NULL</b>.

### -field Settings

### -field Settings.Parallel

### -field Settings.Parallel.NumberOfPresentedRequests

For the parallel <a href="/windows-hardware/drivers/wdf/dispatching-methods-for-i-o-requests">dispatching method</a>, the maximum number of I/O requests that the framework asynchronously delivers to the I/O queue's request handlers. For more information, see the following Remarks section. For the sequential and manual dispatching methods, this member must be zero. This member is available in version 1.9 and later versions of KMDF.

### -field Driver

For internal use only.  Set to NULL. This member is available in version 1.11 and later versions of KMDF.

## -remarks

The driver must initialize the <b>WDF_IO_QUEUE_CONFIG</b> structure by calling <a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_config_init">WDF_IO_QUEUE_CONFIG_INIT</a> or <a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_config_init_default_queue">WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</a>.

The WDF_IO_QUEUE_CONFIG structure is used as an input parameter to <a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuecreate">WdfIoQueueCreate</a>.

Beginning with version 1.9 of KMDF, drivers can use the <b>NumberOfPresentedRequests</b> member to specify the maximum number of I/O requests that the framework asynchronously delivers to a parallel I/O queue's request handlers. After the framework has delivered the specified number of I/O requests to the driver, it does not deliver more requests from the queue until the driver <a href="/windows-hardware/drivers/wdf/completing-i-o-requests">completes</a>, <a href="/windows-hardware/drivers/wdf/canceling-i-o-requests">cancels</a>, or <a href="/windows-hardware/drivers/wdf/requeuing-i-o-requests">requeues</a> at least one of the requests. 

For parallel queues, 
     <a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_config_init">WDF_IO_QUEUE_CONFIG_INIT</a> and <a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_config_init_default_queue">WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE</a> set the <b>NumberOfPresentedRequests</b> member to its default value (-1), which indicates that the framework can deliver an unlimited number of I/O requests to the driver.

## -see-also

[WDF_IO_QUEUE_CONFIG_INIT](./nf-wdfio-wdf_io_queue_config_init.md)

[WDF_IO_QUEUE_CONFIG_INIT_DEFAULT_QUEUE](./nf-wdfio-wdf_io_queue_config_init_default_queue.md)

[WDF_IO_QUEUE_DISPATCH_TYPE](./ne-wdfio-_wdf_io_queue_dispatch_type.md)

[WdfIoQueueCreate](./nf-wdfio-wdfioqueuecreate.md)


[WdfIoQueueReadyNotify](./nf-wdfio-wdfioqueuereadynotify.md)