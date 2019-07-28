---
UID: NS:ksmedia.__unnamed_struct_23
title: KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION (ksmedia.h)
description: The KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION structure appends a buffer base address, a requested buffer size, and a notification count to a KSPROPERTY structure.
old-location: audio\ksrtaudio_buffer_property_with_notification.htm
tech.root: audio
ms.assetid: 767c18e3-4455-4d2b-a71a-23ca11f718c8
ms.date: 05/08/2018
ms.keywords: "*PKSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION, KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION, KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION structure [Audio Devices], PKSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION, PKSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION structure pointer [Audio Devices], aud-prop_43dd73ce-1c4d-4138-a7c1-9f1f17da5643.xml, audio.ksrtaudio_buffer_property_with_notification, ksmedia/KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION, ksmedia/PKSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION"
ms.topic: struct
f1_keywords:
 - "ksmedia/KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION"
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later Windows operating systems.
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION
product:
- Windows
targetos: Windows
req.typenames: KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION, *PKSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION
---

# KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION structure


## -description


The KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION structure appends a buffer base address, a requested buffer size, and a notification count to a <a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure.  This structure is used by the client to request allocation of the audio buffer via <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-rtaudio-buffer-with-notification">KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION</a>.


## -struct-fields




### -field Property

A KSPROPERTY structure that the client initializes appropriately prior to calling KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION.


### -field BaseAddress

Specifies the buffer base address.  Unless the client specifies a base address, this parameter is set to <b>NULL</b>.


### -field RequestedBufferSize

Specifies the buffer size in bytes.  The driver returns the actual size of the allocated buffer in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ns-ksmedia-ksrtaudio_buffer">KSRTAUDIO_BUFFER</a> structure that it returns.


### -field NotificationCount

Specifies the number of notifications per cycle of the cyclic buffer. Currently, the valid values are 1 or 2.  A value of 1 results in notification to registered notification events at the end of the cyclic buffer.  A value of 2 results in notifications at both the mid-point and the end of the cyclic buffer.


## -remarks



The KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION request uses the KSRTAUDIO_BUFFER_PROPERTY_WITH_NOTIFICATION structure to describe the cyclic buffer that the client requests.  The driver returns a KSRTAUDIO_BUFFER structure to describe the buffer actually allocated.

As with KSPROPERTY_RTAUDIO_BUFFER, the value that the client writes into the <b>RequestedBufferSize</b> member is not binding on the driver.

Using KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION facilitates event signaling as DMA progresses through the cyclic buffer.  <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-rtaudio-register-notification-event">KSPROPERTY_RTAUDIO_REGISTER_NOTIFICATION_EVENT</a> is used to register events to receive these notifications and <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-rtaudio-unregister-notification-event">KSPROPERTY_RTAUDIO_UNREGISTER_NOTIFICATION_EVENT</a> is used to unregister events.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-rtaudio-buffer-with-notification">KSPROPERTY_RTAUDIO_BUFFER_WITH_NOTIFICATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-rtaudio-register-notification-event">KSPROPERTY_RTAUDIO_REGISTER_NOTIFICATION_EVENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-rtaudio-unregister-notification-event">KSPROPERTY_RTAUDIO_UNREGISTER_NOTIFICATION_EVENT</a>
 

 

