---
UID: NF:ucxendpoint.UcxEndpointCreate
title: UcxEndpointCreate function (ucxendpoint.h)
description: Creates an endpoint on the specified USB device object.
old-location: buses\_ucxendpointcreate.htm
tech.root: usbref
ms.assetid: 2BB3B2CE-FD15-4D28-BBDA-29C3BB523874
ms.date: 05/07/2018
keywords: ["UcxEndpointCreate function"]
ms.keywords: UcxEndpointCreate, UcxEndpointCreate method [Buses], buses._ucxendpointcreate, ucxendpoint/UcxEndpointCreate
f1_keywords:
 - "ucxendpoint/UcxEndpointCreate"
 - "UcxEndpointCreate"
req.header: ucxendpoint.h
req.include-header: Ucxclass.h, Ucxendpoint.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
- COM
api_location:
- ucxendpoint.h
api_name:
- UcxEndpointCreate
targetos: Windows
req.typenames: 
---

# UcxEndpointCreate function


## -description


Creates an endpoint on the specified USB device object.


## -parameters




### -param UsbDevice [in]

A handle to the USB device object that contains the endpoint. The client driver retrieved the handle in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/nf-ucxusbdevice-ucxusbdevicecreate">UcxUsbDeviceCreate</a>.


### -param EndpointInit [out]

A pointer to a <b>UCXENDPOINT_INIT</b> structure that describes various configuration
        operations for creating the endpoint object. The driver specifies function pointers to its callback functions in this structure.
    This structure is managed by UCX.


### -param Attributes [in, optional]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that specifies attributes for the endpoint object. 


### -param Endpoint [out]

A pointer to a variable that receives a handle to the new endpoint object.


## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code. 




## -remarks



The client driver for the host controller must call this method after the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a> call. The parent of the new endpoint object is the USB device object. 

The method initializes the endpoint object with information such as the type of endpoint, pipe, transfer, and maximum transfers size.

For a code example, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/nc-ucxusbdevice-evt_ucx_usbdevice_endpoint_add">EVT_UCX_USBDEVICE_ENDPOINT_ADD</a>.



