---
UID: NF:portcls.IPortClsNotifications.FreeNotificationBuffer
title: IPortClsNotifications::FreeNotificationBuffer (portcls.h)
description: Frees a previously allocated IPortClsNotifications buffer. The buffer is used in sending notifications, to allow for communications between audio modules and UWP apps.
old-location: audio\iportclsnotifications_freenotification.htm
tech.root: audio
ms.assetid: 93EC2651-3C52-4810-9F7A-A81BC7DA20AF
ms.date: 05/08/2018
ms.keywords: FreeNotificationBuffer, FreeNotificationBuffer method [Audio Devices], FreeNotificationBuffer method [Audio Devices],IPortClsNotifications interface, IPortClsNotifications interface [Audio Devices],FreeNotificationBuffer method, IPortClsNotifications.FreeNotificationBuffer, IPortClsNotifications::FreeNotificationBuffer, audio.iportclsnotifications_freenotification, portcls/IPortClsNotifications::FreeNotificationBuffer
ms.topic: method
f1_keywords:
 - "portcls/IPortClsNotifications.FreeNotificationBuffer"
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 10, version 1703 and later versions of Windows.
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Portcls.lib
- Portcls.dll
api_name:
- IPortClsNotifications.FreeNotificationBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortClsNotifications::FreeNotificationBuffer


## -description


Frees a previously allocated IPortClsNotifications buffer. The buffer is used in sending notifications, to allow for communications between audio modules and UWP apps. 

For more information about audio modules, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/implementing-audio-module-communication">Implementing Audio Module Discovery</a>. 


## -parameters




### -param NotificationBuffer [in]

The address of the notification buffer returned in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iportclsnotifications-allocnotificationbuffer">IPortClsNotifications::AllocNotificationBuffer</a> call.


## -returns



This function returns void.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iportclsnotifications">IPortClsNotifications</a>
 

 

