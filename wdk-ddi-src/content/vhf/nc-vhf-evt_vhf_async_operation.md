---
UID: NC:vhf.EVT_VHF_ASYNC_OPERATION
title: EVT_VHF_ASYNC_OPERATION (vhf.h)
description: The HID source driver implements this event callback if it wants to support one of the four asynchronous operation to get and set HID reports.
old-location: hid\evtvhfasyncoperation.htm
tech.root: hid
ms.assetid: C42174FE-202F-405D-840B-8613762F43AC
ms.date: 04/30/2018
keywords: ["EVT_VHF_ASYNC_OPERATION callback function"]
ms.keywords: EVT_VHF_ASYNC_OPERATION, EVT_VHF_ASYNC_OPERATION callback, EvtVhfAsyncOperation, EvtVhfAsyncOperation callback function [Human Input Devices], hid.evtvhfasyncoperation, vhf/EvtVhfAsyncOperation
req.header: vhf.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_VHF_ASYNC_OPERATION
 - vhf/EVT_VHF_ASYNC_OPERATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - vhf.h
api_name:
 - EvtVhfAsyncOperation
---

# EVT_VHF_ASYNC_OPERATION callback function


## -description

The HID source driver implements this event callback if it wants to support one of the four asynchronous operation to get and set HID reports.

## -parameters

### -param VhfClientContext 

[in]
An opaque pointer to a HID source driver-defined buffer that the driver passed in the <a href="/windows-hardware/drivers/ddi/vhf/ns-vhf-_vhf_config">VHF_CONFIG</a> structure supplied to <a href="/windows-hardware/drivers/ddi/vhf/nf-vhf-vhfcreate">VhfCreate</a> to create the virtual HID device.

### -param VhfOperationHandle 

[in]
An opaque handle that uniquely identifies this asynchronous operation.

### -param VhfOperationContext 

[in, optional]
Pointer to a buffer that can be used by the HID source driver for servicing the operation. Size of the buffer is specified by the HID source driver in the <a href="/windows-hardware/drivers/ddi/vhf/ns-vhf-_vhf_config">VHF_CONFIG</a> structure supplied to <a href="/windows-hardware/drivers/ddi/vhf/nf-vhf-vhfcreate">VhfCreate</a>.

### -param HidTransferPacket 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/hidclass/ns-hidclass-_hid_xfer_packet">HID_XFER_PACKET</a> structure. Contains information about a HID Report and is used by the HID source driver and the HID class/mini driver pair for I/O requests to get or set a report.

## -remarks

There are four types of asynchronous operations that your HID source driver can support: <b>GetFeature</b>, <b>SetFeature</b>, <b>WriteReport</b>, <b>GetInputReport</b>. 

<div class="alert"><b>Note</b>  Those operations are analogous to <a href="/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_feature">IOCTL_HID_GET_FEATURE</a>, <a href="/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_set_feature">IOCTL_HID_SET_FEATURE</a>, <a href="/previous-versions/hh439646(v=vs.85)">IOCTL_HID_WRITE_REPORT</a>, <a href="/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_input_report">IOCTL_HID_GET_INPUT_REPORT</a> requests that a HID transport minidriver implements.</div>
<div> </div>
To support such an operation, the HID source driver must implement an <i>EvtVhfAsyncOperation</i> callback function and register it with the Virtual HID Framework (VHF) in the driver's call to <a href="/windows-hardware/drivers/ddi/vhf/nf-vhf-vhfcreate">VhfCreate</a> function after calling <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>.  For example, for <b>GetFeature</b>, the driver must implement  <i>EvtVhfAsyncOperation</i> and set the <b>EvtVhfAsyncOperationGetFeature</b> member of the <a href="/windows-hardware/drivers/ddi/vhf/ns-vhf-_vhf_config">VHF_CONFIG</a> to a function pointer of the implemented function.

When VHF gets a request that sets or queries a HID Report, VHF invokes the previously-registered <i>EvtVhfAsyncOperation</i> callback function and an asynchronous operation starts. Each operation is identified by a VHFOPERATIONHANDLE handle that is set by VHF. If the driver specified a non-zero value in the <b>OperationContextSize</b> member of the <a href="/windows-hardware/drivers/ddi/vhf/ns-vhf-_vhf_config">VHF_CONFIG</a> during initialization, VHF allocates a buffer of that size and passes a pointer to that buffer  in the <i>VhfOperationContext</i> parameter when it invokes  <i>EvtVhfAsyncOperation</i>. 

<i>HidTransferPacket</i> is the transfer buffer for this operation that points to a VHF-allocated structure containing HID Report-specific details. For example, if the operation is <b>GetFeature</b>, upon completion the buffer is filled by  the HID source driver with the requested HID Feature Report.

When the operation is complete, HID source calls <a href="/windows-hardware/drivers/ddi/vhf/nf-vhf-vhfasyncoperationcomplete">VhfAsyncOperationComplete</a> to report the completion status.

## -see-also

<a href="/windows-hardware/drivers/hid/virtual-hid-framework--vhf-">Write a HID source driver by using Virtual HID Framework (VHF)</a>