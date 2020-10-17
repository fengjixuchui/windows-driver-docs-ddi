---
UID: NF:strmini.StreamClassAbortOutstandingRequests
title: StreamClassAbortOutstandingRequests function (strmini.h)
description: The StreamClassAbortOutstandingRequests routine aborts all outstanding requests, either to a particular stream, or to the entire driver.
old-location: stream\streamclassabortoutstandingrequests.htm
tech.root: stream
ms.assetid: d60ef96b-d145-48e5-be56-7f0bc4d1d0f3
ms.date: 04/23/2018
keywords: ["StreamClassAbortOutstandingRequests function"]
ms.keywords: StreamClassAbortOutstandingRequests, StreamClassAbortOutstandingRequests routine [Streaming Media Devices], strclass-routines_f0bb32ce-019d-4c2f-90f6-cf6d54e2fb08.xml, stream.streamclassabortoutstandingrequests, strmini/StreamClassAbortOutstandingRequests
req.header: strmini.h
req.include-header: Strmini.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: Stream.lib
req.dll: 
req.irql: Greater than DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - StreamClassAbortOutstandingRequests
 - strmini/StreamClassAbortOutstandingRequests
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Stream.lib
 - Stream.dll
api_name:
 - StreamClassAbortOutstandingRequests
---

# StreamClassAbortOutstandingRequests function


## -description

The <b>StreamClassAbortOutstandingRequests</b> routine aborts all outstanding requests, either to a particular stream, or to the entire driver.

## -parameters

### -param HwDeviceExtension 

[in]
Pointer to the minidriver's device extension. The minidriver specifies the size of this buffer in the <a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself via <a href="/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassregisteradapter">StreamClassRegisterMinidriver</a>. The class driver then passes pointers to the buffer in the <b>HwDeviceExtension</b> member of the <a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_request_block">HW_STREAM_REQUEST_BLOCK</a>, <a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_object">HW_STREAM_OBJECT</a>, <a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_time_context">HW_TIME_CONTEXT</a>, and <a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_port_configuration_information">PORT_CONFIGURATION_INFORMATION</a> structures it passes to the minidriver.

### -param HwStreamObject 

[in, optional]
Pointer to a <a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_object">HW_STREAM_OBJECT</a> that specifies which stream to abort requests on, or <b>NULL</b> to abort all requests to the minidriver. If this parameter is <b>NULL</b>, all device and stream requests are canceled.

### -param Status 

[in]
Specifies the status to be returned when an outstanding request is aborted.

## -remarks

This call also signals the class driver that the minidriver is ready to receive new requests of the type canceled.