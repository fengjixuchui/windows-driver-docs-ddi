---
UID: NE:wdfrequest._WDF_REQUEST_STOP_ACTION_FLAGS
title: _WDF_REQUEST_STOP_ACTION_FLAGS (wdfrequest.h)
description: The WDF_REQUEST_STOP_ACTION_FLAGS enumeration type defines flags that the framework passes to a driver's EvtIoStop callback function.
old-location: wdf\wdf_request_stop_action_flags.htm
tech.root: wdf
ms.assetid: 01f95aee-60aa-4d6f-88a9-c0fa6ea6a09a
ms.date: 02/26/2018
keywords: ["WDF_REQUEST_STOP_ACTION_FLAGS enumeration"]
ms.keywords: DFRequestObjectRef_e291c6a5-1e65-4505-9090-19e6ea66e7b3.xml, WDF_REQUEST_STOP_ACTION_FLAGS, WDF_REQUEST_STOP_ACTION_FLAGS enumeration, WdfRequestStopActionInvalid, WdfRequestStopActionPurge, WdfRequestStopActionSuspend, WdfRequestStopRequestCancelable, _WDF_REQUEST_STOP_ACTION_FLAGS, kmdf.wdf_request_stop_action_flags, wdf.wdf_request_stop_action_flags, wdfrequest/WDF_REQUEST_STOP_ACTION_FLAGS, wdfrequest/WdfRequestStopActionInvalid, wdfrequest/WdfRequestStopActionPurge, wdfrequest/WdfRequestStopActionSuspend, wdfrequest/WdfRequestStopRequestCancelable
req.header: wdfrequest.h
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
req.typenames: WDF_REQUEST_STOP_ACTION_FLAGS
f1_keywords:
 - _WDF_REQUEST_STOP_ACTION_FLAGS
 - wdfrequest/_WDF_REQUEST_STOP_ACTION_FLAGS
 - WDF_REQUEST_STOP_ACTION_FLAGS
 - wdfrequest/WDF_REQUEST_STOP_ACTION_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfrequest.h
api_name:
 - WDF_REQUEST_STOP_ACTION_FLAGS
---

# _WDF_REQUEST_STOP_ACTION_FLAGS enumeration (wdfrequest.h)


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_REQUEST_STOP_ACTION_FLAGS</b> enumeration type defines flags that the framework passes to a driver's <a href="/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_stop">EvtIoStop</a> callback function.

## -enum-fields

### -field WdfRequestStopActionInvalid

Reserved for internal use only.

### -field WdfRequestStopActionSuspend

The framework is stopping the I/O queue because the device is leaving its working (D0) state.

### -field WdfRequestStopActionPurge

The framework is stopping the I/O queue because the device is being removed.

### -field WdfRequestStopRequestCancelable

The I/O request is cancelable.

## -remarks

When the framework calls a driver's <a href="/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_stop">EvtIoStop</a> callback function, it sets either the <b>WdfRequestStopActionSuspend</b> or <b>WdfRequestStopActionPurge</b> flag. If the request is cancelable, the framework also sets the <b>WdfRequestStopRequestCancelable</b> flag.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_stop">EvtIoStop</a>