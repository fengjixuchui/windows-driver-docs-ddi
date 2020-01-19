---
UID: NF:video.VideoPortQuerySystemTime
title: VideoPortQuerySystemTime function (video.h)
description: The VideoPortQuerySystemTime function obtains the current system time.
old-location: display\videoportquerysystemtime.htm
tech.root: display
ms.assetid: d9b54710-6ad2-4959-9172-76c90468d343
ms.date: 05/10/2018
ms.keywords: VideoPortQuerySystemTime, VideoPortQuerySystemTime function [Display Devices], VideoPort_Functions_18c4e015-b294-40e0-8aef-7642d3a9cb27.xml, display.videoportquerysystemtime, video/VideoPortQuerySystemTime
ms.topic: function
f1_keywords:
 - "video/VideoPortQuerySystemTime"
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortQuerySystemTime
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortQuerySystemTime function


## -description


The <b>VideoPortQuerySystemTime</b> function obtains the current system time.


## -parameters




### -param CurrentTime [out]

Pointer to a memory location that will receive the current system time.


## -returns



None




## -remarks



System time is a count of 100-nanosecond intervals since January 1, 1601. System time is typically updated approximately every ten milliseconds. This value is computed for the GMT time zone. To adjust this value for the local time zone use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exsystemtimetolocaltime">ExSystemTimeToLocalTime</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportqueryperformancecounter">VideoPortQueryPerformanceCounter</a>
 

 

