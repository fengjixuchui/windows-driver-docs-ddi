---
UID: NF:sti.IStiDevice.UnSubscribe
title: IStiDevice::UnSubscribe (sti.h)
description: The IStiDevice::UnSubscribe method removes the caller from the list of applications registered to receive notification of device events.
old-location: image\istidevice_unsubscribe.htm
tech.root: image
ms.assetid: ee0bfafa-9f4b-4b4a-8b26-4bab81253500
ms.date: 05/03/2018
ms.keywords: IStiDevice interface [Imaging Devices],UnSubscribe method, IStiDevice.UnSubscribe, IStiDevice::UnSubscribe, UnSubscribe, UnSubscribe method [Imaging Devices], UnSubscribe method [Imaging Devices],IStiDevice interface, image.istidevice_unsubscribe, sti/IStiDevice::UnSubscribe, stifnc_8144319d-d1da-40cd-ad1d-6b65c28155be.xml
ms.topic: method
f1_keywords:
 - "sti/IStiDevice.UnSubscribe"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Sti.h
api_name:
- IStiDevice.UnSubscribe
product:
- Windows
targetos: Windows
req.typenames: 
---

# IStiDevice::UnSubscribe


## -description


The<b> IStiDevice::UnSubscribe</b> method removes the caller from the list of applications registered to receive notification of device events.


## -parameters






## -returns



If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



Before calling <b>IStiDevice::UnSubscribe</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543778(v=vs.85)">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_image/index">IStiDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sti/nf-sti-istidevice-subscribe">IStiDevice::Subscribe</a>
 

 

