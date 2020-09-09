---
UID: NF:sti.IStiDevice.GetLastNotificationData
title: IStiDevice::GetLastNotificationData (sti.h)
description: The IStiDevice::GetLastNotificationData method returns a description of the most recent event that occurred on a still image device.
old-location: image\istidevice_getlastnotificationdata.htm
tech.root: image
ms.assetid: dd073fde-d2ba-45c0-a52c-22e86718901a
ms.date: 05/03/2018
keywords: ["IStiDevice::GetLastNotificationData"]
ms.keywords: GetLastNotificationData, GetLastNotificationData method [Imaging Devices], GetLastNotificationData method [Imaging Devices],IStiDevice interface, IStiDevice interface [Imaging Devices],GetLastNotificationData method, IStiDevice.GetLastNotificationData, IStiDevice::GetLastNotificationData, image.istidevice_getlastnotificationdata, sti/IStiDevice::GetLastNotificationData, stifnc_def72c8c-f8cf-4eb7-84a1-e99ecddee4de.xml
req.header: sti.h
req.include-header: Sti.h
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IStiDevice::GetLastNotificationData
 - sti/IStiDevice::GetLastNotificationData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - sti.h
api_name:
 - IStiDevice.GetLastNotificationData
---

# IStiDevice::GetLastNotificationData


## -description

The <b>IStiDevice::GetLastNotificationData</b> method returns a description of the most recent event that occurred on a still image device.

## -parameters

### -param lpNotify 

[out]
Caller-supplied pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/ns-sti-_stinotify">STINOTIFY</a> structure to receive event information.

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## -remarks

Each time a <a href="https://docs.microsoft.com/windows-hardware/drivers/image/still-image-device-events">Still Image Device Events</a> occurs, the still image event monitor calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-getnotificationdata">IStiUSD::GetNotificationData</a> (exported by a vendor-supplied minidriver) to obtain an event description. These descriptions are added to a linked list. If a client of the <b>IStiDevice</b> COM interface has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-subscribe">IStiDevice::Subscribe</a>, it is notified each time a device event occurs. It can then call <b>IStiDevice::GetLastNotificationData</b> to obtain the most recent addition to the linked list of events.

Before calling <b>IStiDevice::GetLastNotificationData</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543778(v=vs.85)">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.

