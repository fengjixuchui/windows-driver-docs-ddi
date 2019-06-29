---
UID: NC:ucxusbdevice.EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD
title: EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD (ucxusbdevice.h)
description: The client driver's implementation that UCX calls to add a new default endpoint for a USB device.
old-location: buses\evt_ucx_usbdevice_default_endpoint_add.htm
tech.root: usbref
ms.assetid: b9c38199-810a-462b-a805-9751de2a419e
ms.date: 05/07/2018
ms.keywords: EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD, EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD callback, EvtUcxUsbDeviceDefaultEndpointAdd, EvtUcxUsbDeviceDefaultEndpointAdd callback function [Buses], PEVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD, PEVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD callback function pointer [Buses], buses.evt_ucx_usbdevice_default_endpoint_add, ucxusbdevice/EvtUcxUsbDeviceDefaultEndpointAdd
ms.topic: callback
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ucxusbdevice.h
api_name:
- PEVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD callback function


## -description


The client driver's implementation that UCX calls to add a new default endpoint for a USB device.


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a> method.


### -param UcxUsbDevice [in]

A handle to a UCX object that represents the USB device.


### -param MaxPacketSize [in]

Maximum packet size for transfers on this endpoint.


### -param UcxEndpointInit








#### - EndpointInit [in]

A pointer to an opaque structure containing initialization
        information.  Callbacks for the endpoint object are associated with this
        structure.  This structure is managed by UCX.


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.




## -remarks



The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxusbdevice/nf-ucxusbdevice-ucxusbdevicecreate">UcxUsbDeviceCreate</a> method.

The callback function calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a> to create a new default endpoint object and register its default endpoint object callback functions.

Then, the callback  function typically creates a WDF queue associated with the endpoint
    object.   The  queue does not receive any requests until the class extension
    starts it.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
Endpoint_EvtUcxUsbDeviceDefaultEndpointAdd(
    UCXCONTROLLER           UcxController,
    UCXUSBDEVICE            UcxUsbDevice,
    ULONG                   MaxPacketSize,
    PUCXENDPOINT_INIT       EndpointInit
)

{
    NTSTATUS                                status = STATUS_SUCCESS;

    UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS    ucxDefaultEndpointEventCallbacks;
    WDF_OBJECT_ATTRIBUTES                   objectAttributes;

    PUCX_CONTROLLER_CONTEXT                 ucxControllerContext;

    UCXENDPOINT                             ucxEndpoint;
    PUCX_ENDPOINT_CONTEXT                   ucxEndpointContext;


    WDF_IO_QUEUE_CONFIG                     queueConfig;
    WDFQUEUE                                wdfQueue;


    UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS_INIT(&ucxDefaultEndpointEventCallbacks,
                                              Endpoint_EvtUcxEndpointPurge,
                                              Endpoint_EvtUcxEndpointStart,
                                              Endpoint_EvtUcxEndpointAbort,
                                              Endpoint_EvtUcxEndpointOkToCancelTransfers,
                                              Endpoint_EvtUcxDefaultEndpointUpdate,
                                              Endpoint_EvtUcxEndpointEnableForwardProgress);

    UcxDefaultEndpointInitSetEventCallbacks(EndpointInit, &ucxDefaultEndpointEventCallbacks);

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&objectAttributes, UCX_ENDPOINT_CONTEXT);

    ucxControllerContext = GetUcxControllerContext(UcxController);

    status = UcxEndpointCreate(UcxUsbDevice,
        &EndpointInit,
        &objectAttributes,
        &ucxEndpoint);

    if (!NT_SUCCESS(status)) {
        DbgTrace(TL_ERROR, Endpoint, "UcxEndpoint Failed %!STATUS!", status);
        goto EvtUsbDeviceDefaultEndpointAddEnd;
    }

    DbgTrace(TL_INFO, Endpoint, "UcxEndpoint created");

    ucxEndpointContext = GetUcxEndpointContext(ucxEndpoint);

    ucxEndpointContext->IsDefault = TRUE;
    ucxEndpointContext->MaxPacketSize = MaxPacketSize;

    WDF_IO_QUEUE_CONFIG_INIT(&queueConfig, WdfIoQueueDispatchManual);

    status = WdfIoQueueCreate(ucxControllerContext->WdfDevice,
        &queueConfig,
        WDF_NO_OBJECT_ATTRIBUTES,
        &wdfQueue);

    if (!NT_SUCCESS(status)) {
        DbgTrace(TL_ERROR, Endpoint, "WdfIoQueueCreate Failed %!STATUS!", status);
        goto EvtUsbDeviceDefaultEndpointAddEnd;
    }

    UcxEndpointSetWdfIoQueue(ucxEndpoint, wdfQueue);

EvtUsbDeviceDefaultEndpointAddEnd:

    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxendpoint/nf-ucxendpoint-ucx_default_endpoint_event_callbacks_init">UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxendpoint/nf-ucxendpoint-ucxdefaultendpointinitseteventcallbacks">UcxDefaultEndpointInitSetEventCallbacks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxendpoint/nf-ucxendpoint-ucxendpointcreate">UcxEndpointCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxusbdevice/nf-ucxusbdevice-ucxusbdevicecreate">UcxUsbDeviceCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdf_io_queue_config_init">WDF_IO_QUEUE_CONFIG_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdfioqueuecreate">WdfIoQueueCreate</a>
 

 

