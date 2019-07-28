---
UID: NC:video.PMINIPORT_DPC_ROUTINE
title: PMINIPORT_DPC_ROUTINE (video.h)
description: The HwVidDpcRoutine function is a miniport driver-implemented callback that is called when a queued DPC gets scheduled.
old-location: display\hwviddpcroutine.htm
tech.root: display
ms.assetid: d4b443a2-3665-4e7c-b84a-5388a8fe8681
ms.date: 05/10/2018
ms.keywords: HwVidDpcRoutine, HwVidDpcRoutine callback function [Display Devices], PMINIPORT_DPC_ROUTINE, PMINIPORT_DPC_ROUTINE callback, VideoMiniport_Functions_5d605867-89d7-44a9-b08b-c49ffaa90244.xml, display.hwviddpcroutine, video/HwVidDpcRoutine
ms.topic: callback
f1_keywords:
 - "video/HwVidDpcRoutine"
req.header: video.h
req.include-header: Video.h
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
- UserDefined
api_location:
- video.h
api_name:
- HwVidDpcRoutine
product:
- Windows
targetos: Windows
req.typenames: 
---

# PMINIPORT_DPC_ROUTINE callback function


## -description


<i>The HwVidDpcRoutine</i> function is a miniport driver-implemented callback that is called when a queued DPC gets scheduled.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's hardware device extension. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/device-extensions">Device Extensions</a>.


### -param Context [in]

Contains any miniport driver-supplied data this function may need. <i>Context</i> can be <b>NULL</b> if the DPC implementation does not require additional information.


## -returns



None




## -remarks



The miniport driver queues this DPC by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportqueuedpc">VideoPortQueueDpc</a>.

Because <i>HwVidDpcRoutine </i>is called at DISPATCH_LEVEL, it must not manipulate any pageable code or data. Further, this function must be in nonpaged memory and should complete its operations as quickly as possible.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportqueuedpc">VideoPortQueueDpc</a>
 

 

