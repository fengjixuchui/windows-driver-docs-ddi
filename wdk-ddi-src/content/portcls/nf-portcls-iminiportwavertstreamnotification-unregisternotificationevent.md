---
UID: NF:portcls.IMiniportWaveRTStreamNotification.UnregisterNotificationEvent
title: IMiniportWaveRTStreamNotification::UnregisterNotificationEvent (portcls.h)
description: The UnregisterNotificationEvent method unregisters an event from DMA driven event notification.
old-location: audio\iminiportwavertstreamnotification_unregisternotificationevent.htm
tech.root: audio
ms.assetid: 5b264784-7680-4c3b-9fc7-0609c53b53a2
ms.date: 05/08/2018
keywords: ["IMiniportWaveRTStreamNotification::UnregisterNotificationEvent"]
ms.keywords: IMiniportWaveRTStreamNotification interface [Audio Devices],UnregisterNotificationEvent method, IMiniportWaveRTStreamNotification.UnregisterNotificationEvent, IMiniportWaveRTStreamNotification::UnregisterNotificationEvent, UnregisterNotificationEvent, UnregisterNotificationEvent method [Audio Devices], UnregisterNotificationEvent method [Audio Devices],IMiniportWaveRTStreamNotification interface, audio.iminiportwavertstreamnotification_unregisternotificationevent, audmp-routines_db635e04-50ae-4aed-b5a5-dfb33f14d153.xml, portcls/IMiniportWaveRTStreamNotification::UnregisterNotificationEvent
req.header: portcls.h
req.include-header: 
req.target-type: Universal
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
req.irql: Passive level.
targetos: Windows
req.typenames: 
f1_keywords:
 - IMiniportWaveRTStreamNotification::UnregisterNotificationEvent
 - portcls/IMiniportWaveRTStreamNotification::UnregisterNotificationEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IMiniportWaveRTStreamNotification.UnregisterNotificationEvent
---

# IMiniportWaveRTStreamNotification::UnregisterNotificationEvent


## -description

The <code>UnregisterNotificationEvent</code> method unregisters an event from DMA driven event notification.

## -parameters

### -param NotificationEvent 

[in]
A pointer to a previously registered kernel event (PKEVENT) to be unregistered from notification as DMA progresses.

## -returns

<code>UnregisterNotificationEvent</code> returns a status value of STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error status code.

## -remarks

The port driver calls this method in response to a <a href="/windows-hardware/drivers/audio/ksproperty-rtaudio-unregister-notification-event">KSPROPERTY_RTAUDIO_UNREGISTER_NOTIFICATION_EVENT</a> property request from a client.  The port driver maps the user-mode event handle to a kernel event pointer and passes the pointer in with the <i>NotificationEvent</i> parameter.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportwavertstreamnotification">IMiniportWaveRTStreamNotification</a>



<a href="/windows-hardware/drivers/audio/ksproperty-rtaudio-unregister-notification-event">KSPROPERTY_RTAUDIO_UNREGISTER_NOTIFICATION_EVENT</a>