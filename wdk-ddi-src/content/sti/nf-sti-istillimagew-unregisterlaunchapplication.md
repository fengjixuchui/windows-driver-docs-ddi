---
UID: NF:sti.IStillImageW.UnregisterLaunchApplication
title: IStillImageW::UnregisterLaunchApplication (sti.h)
description: The IStillImage::UnregisterLaunchApplication method removes an application from the still image event monitor's list of push-model aware applications.
old-location: image\istillimage_unregisterlaunchapplication.htm
tech.root: image
ms.assetid: cf57265a-d343-4e49-9635-6a4663c9a3a5
ms.date: 05/03/2018
keywords: ["IStillImageW::UnregisterLaunchApplication"]
ms.keywords: IStillImageW interface [Imaging Devices],UnregisterLaunchApplication method, IStillImageW.UnregisterLaunchApplication, IStillImageW::UnregisterLaunchApplication, UnregisterLaunchApplication, UnregisterLaunchApplication method [Imaging Devices], UnregisterLaunchApplication method [Imaging Devices],IStillImageW interface, image.istillimage_unregisterlaunchapplication, sti/IStillImageW::UnregisterLaunchApplication, stifnc_7e477efa-efa3-445d-bd68-a23f87cee5de.xml
f1_keywords:
 - "sti/IStillImageW.UnregisterLaunchApplication"
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
- sti.h
api_name:
- IStillImageW.UnregisterLaunchApplication
product:
- Windows
targetos: Windows
req.typenames: 
---

# IStillImageW::UnregisterLaunchApplication


## -description


The <b>IStillImage::UnregisterLaunchApplication</b> method removes an application from the still image event monitor's list of push-model aware applications.


## -parameters




### -param pwszAppName [in]

Caller-supplied pointer to the application's "short name".


## -returns



If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



The <b>IStillImage::UnRegisterLaunchApplication</b> method should be called as part of the process of uninstalling a push-model aware application. The method can be uninstalled either by the application itself or by other uninstalling software.

Before calling <b>IStillImage::UnRegisterLaunchApplication</b>, clients of the <b>IStillImage</b> COM interface must call <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543804(v=vs.85)">IStillImage::StiCreateInstance</a> to obtain an <b>IStillImage</b> interface pointer.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543798(v=vs.85)">IStillImage::RegisterLaunchApplication</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_image/index">IStillImageW</a>
 

 

