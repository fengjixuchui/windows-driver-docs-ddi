---
UID: NF:strmini.StreamClassDeviceNotification
title: StreamClassDeviceNotification function (strmini.h)
description: Minidrivers use the StreamClassDeviceNotification routine to notify the class driver that it has completed a stream request, or that an event has occurred.
old-location: stream\streamclassdevicenotification.htm
tech.root: stream
ms.assetid: 80383159-c2c3-4d05-92e8-9245408e5243
ms.date: 04/23/2018
ms.keywords: StreamClassDeviceNotification, StreamClassDeviceNotification routine [Streaming Media Devices], strclass-routines_bddec484-f87c-4ebc-b8e1-ea52d265cbc4.xml, stream.streamclassdevicenotification, strmini/StreamClassDeviceNotification
ms.topic: function
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Stream.lib
- Stream.dll
api_name:
- StreamClassDeviceNotification
product:
- Windows
targetos: Windows
req.typenames: 
---

# StreamClassDeviceNotification function


## -description


Minidrivers use the <b>StreamClassDeviceNotification</b> routine to notify the class driver that it has completed a stream request, or that an event has occurred.


## -parameters




### -param NotificationType [in]

This is an enumeration value that contains the type of notification that the minidriver is sending.





#### DeviceRequestComplete

Indicates that the minidriver has completed its handling of the device stream request block pointed to by the optional third argument of this routine, <i>pSrb</i>. Once the minidriver calls <b>StreamClassDeviceNotification</b> with this value, the relevant SRB is owned by the class driver, which is free to deallocate it.



#### ReadyForNextDeviceRequest

Indicates that the minidriver is ready to receive another device request. 



#### SignalDeviceEvent

Signals that the event specified by the <i>EventEntry</i> parameter has occurred.



#### SignalMultipleDeviceEvents

Signals all events that match the criteria specified in the <i>EventSet</i> and <i>EventId</i> parameters.



#### DeleteDeviceEvent

Deletes the event specified by the <i>EventEntry</i> parameter. 


### -param HwDeviceExtension [in]

Pointer to the minidriver's device extension. The minidriver specifies the size of this buffer in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself via <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/nf-strmini-streamclassregisteradapter">StreamClassRegisterMinidriver</a>. The class driver then passes pointers to the buffer in the <b>HwDeviceExtension</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_hw_stream_request_block">HW_STREAM_REQUEST_BLOCK</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_hw_stream_object">HW_STREAM_OBJECT</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_hw_time_context">HW_TIME_CONTEXT</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_port_configuration_information">PORT_CONFIGURATION_INFORMATION</a> structures it passes to the minidriver.


### -param param






#### - EventEntry

If <i>NotificationType</i> equals either SignalDeviceEvent or DeleteDeviceEvent, points to a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksevent_entry">KSEVENT_ENTRY</a> that specifies the event to be signaled or deleted. 


#### - EventId

Specifies the event ID to match against in the device event queue if <i>NotificationType</i> equals <b>SignalMultipleDeviceEvents</b>.


#### - EventSet

Specifies the event set to match against in the device event queue if <i>NotificationType</i> equals <b>SignalMultipleDeviceEvents</b>. 


#### - pSrb

Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_hw_stream_request_block">HW_STREAM_REQUEST_BLOCK</a> structure. If <i>NotificationType</i> equals <b>DeviceRequestComplete</b>, this parameter points to the stream request block that the minidriver has completed processing. After <b>StreamClassDeviceNotification</b> completes, this address is no longer valid.


## -returns



None




## -remarks



The minidriver uses this routine for requests or events that apply to the minidriver as a whole. Stream-specific requests or events use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/nf-strmini-streamclassstreamnotification">StreamClassStreamNotification</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/nf-strmini-streamclassstreamnotification">StreamClassStreamNotification</a>
 

 

