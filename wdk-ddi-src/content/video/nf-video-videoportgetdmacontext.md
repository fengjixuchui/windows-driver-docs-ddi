---
UID: NF:video.VideoPortGetDmaContext
title: VideoPortGetDmaContext function (video.h)
description: The VideoPortGetDmaContext function is obsolete in Windows 2000 and later.VideoPortGetDmaContext gets the context previously associated with the specified DMA handle.
old-location: display\videoportgetdmacontext.htm
tech.root: display
ms.assetid: 1bd9a156-a366-4f35-956f-d195c41ae722
ms.date: 05/10/2018
keywords: ["VideoPortGetDmaContext function"]
ms.keywords: VideoPortGetDmaContext, VideoPortGetDmaContext function [Display Devices], VideoPort_Functions_97335d32-fa36-4130-a050-39fbdfc08517.xml, display.videoportgetdmacontext, video/VideoPortGetDmaContext
f1_keywords:
 - "video/VideoPortGetDmaContext"
 - "VideoPortGetDmaContext"
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortGetDmaContext
targetos: Windows
req.typenames: 
---

# VideoPortGetDmaContext function


## -description


The <b>VideoPortGetDmaContext</b> function is <b>obsolete</b> in Windows 2000 and later.

<b>VideoPortGetDmaContext</b> gets the context previously associated with the specified DMA handle.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param pDma [in]

Pointer to a DMA handle. To obtain the appropriate DMA handle, use the value in the <b>OutputBuffer</b> member of the <i>pVrp</i> parameter after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportlockpages">VideoPortLockPages</a> returns. 


## -returns



<b>VideoPortGetDmaContext</b> always returns <b>NULL</b>.




## -remarks



See <a href="https://docs.microsoft.com/windows-hardware/drivers/display/bus-master-dma-in-video-miniport-drivers">Bus-Master DMA in Video Miniport Drivers</a> for information about packet-based and common-buffer DMA transfers.



