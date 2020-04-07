---
UID: NE:wdfdevice._WDF_DISPATCH_IRP_TO_IO_QUEUE_FLAGS
title: _WDF_DISPATCH_IRP_TO_IO_QUEUE_FLAGS (wdfdevice.h)
description: The WDF_DISPATCH_IRP_TO_IO_QUEUE_FLAGS enumeration type defines flags that the driver can specify when it calls WdfDeviceWdmDispatchIrpToIoQueue.
old-location: wdf\wdf_dispatch_irp_to_io_queue_flags.htm
tech.root: wdf
ms.assetid: 6A205F51-990F-4721-B4C7-B96E944D2A54
ms.date: 02/26/2018
keywords: ["_WDF_DISPATCH_IRP_TO_IO_QUEUE_FLAGS enumeration"]
ms.keywords: WDF_DISPATCH_IRP_TO_IO_QUEUE_FLAGS, WDF_DISPATCH_IRP_TO_IO_QUEUE_INVOKE_INCALLERCTX_CALLBACK, WDF_DISPATCH_IRP_TO_IO_QUEUE_NO_FLAGS, WDF_DISPATCH_IRP_TO_IO_QUEUE_PREPROCESSED_IRP, WDF_FORWARD_IRP_TO_IO_QUEUE_FLAGS, WDF_FORWARD_IRP_TO_IO_QUEUE_FLAGS enumeration, _WDF_DISPATCH_IRP_TO_IO_QUEUE_FLAGS, kmdf.wdf_dispatch_irp_to_io_queue_flags, kmdf.wdf_forward_irp_to_io_queue_flags, kmdf.wdf_forward_irp_to_io_queue_options_flags, wdf.wdf_dispatch_irp_to_io_queue_flags, wdfdevice/WDF_DISPATCH_IRP_TO_IO_QUEUE_INVOKE_INCALLERCTX_CALLBACK, wdfdevice/WDF_DISPATCH_IRP_TO_IO_QUEUE_NO_FLAGS, wdfdevice/WDF_DISPATCH_IRP_TO_IO_QUEUE_PREPROCESSED_IRP, wdfdevice/WDF_FORWARD_IRP_TO_IO_QUEUE_FLAGS
f1_keywords:
 - "wdfdevice/WDF_DISPATCH_IRP_TO_IO_QUEUE_FLAGS"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfdevice.h
api_name:
- WDF_DISPATCH_IRP_TO_IO_QUEUE_FLAGS
product:
- Windows
targetos: Windows
req.typenames: WDF_DISPATCH_IRP_TO_IO_QUEUE_FLAGS
---

# _WDF_DISPATCH_IRP_TO_IO_QUEUE_FLAGS enumeration


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_DISPATCH_IRP_TO_IO_QUEUE_FLAGS</b> enumeration type defines flags that the driver can specify when it calls  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmdispatchirptoioqueue">WdfDeviceWdmDispatchIrpToIoQueue</a>.


## -enum-fields




### -field WDF_DISPATCH_IRP_TO_IO_QUEUE_NO_FLAGS

No flags are set.


### -field WDF_DISPATCH_IRP_TO_IO_QUEUE_INVOKE_INCALLERCTX_CALLBACK

Specifies that the framework should call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_io_in_caller_context">EvtIoInCallerContext</a> callback function before inserting the request into the queue.


### -field WDF_DISPATCH_IRP_TO_IO_QUEUE_PREPROCESSED_IRP

Specifies that the IRP was preprocessed by the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess">EvtDeviceWdmIrpPreprocess</a> callback function.  Accordingly, the framework adjusts the IRP's stack location to the next entry before inserting it into the queue.


## -remarks



 For more information about specifying queues for IRPs as they arrive, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dispatching-irps-to-i-o-queues">Dispatching IRPs to I/O Queues</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess">EvtDeviceWdmIrpPreprocess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmdispatchirptoioqueue">WdfDeviceWdmDispatchIrpToIoQueue</a>
 

 

