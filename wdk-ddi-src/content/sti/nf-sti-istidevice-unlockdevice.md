---
UID: NF:sti.IStiDevice.UnLockDevice
title: IStiDevice::UnLockDevice (sti.h)
description: The IStiDevice::UnLockDevice method unlocks a device that was locked by a previous call to IStiDevice::LockDevice.
old-location: image\istidevice_unlockdevice.htm
tech.root: image
ms.assetid: 0bcd48c6-be8a-47af-9e34-a06ce572925c
ms.date: 05/03/2018
ms.keywords: IStiDevice interface [Imaging Devices],UnLockDevice method, IStiDevice.UnLockDevice, IStiDevice::UnLockDevice, UnLockDevice, UnLockDevice method [Imaging Devices], UnLockDevice method [Imaging Devices],IStiDevice interface, image.istidevice_unlockdevice, sti/IStiDevice::UnLockDevice, stifnc_7f72c1a7-41cd-4191-8c8f-390dfc991246.xml
ms.topic: method
f1_keywords:
 - "sti/IStiDevice.UnLockDevice"
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
- IStiDevice.UnLockDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IStiDevice::UnLockDevice


## -description


The <b>IStiDevice::UnLockDevice</b> method unlocks a device that was locked by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sti/nf-sti-istidevice-lockdevice">IStiDevice::LockDevice</a>.


## -parameters






## -returns



If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



Before the <b>IStiDevice::UnLockDevice</b> method releases the <b>IStiDevice</b>-level lock on the device, it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/stiusd/nf-stiusd-istiusd-unlockdevice">IStiUSD::UnLockDevice</a> in the appropriate vendor-supplied minidriver.

Before calling <b>IStiDevice::UnLockDevice</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543778(v=vs.85)">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.



