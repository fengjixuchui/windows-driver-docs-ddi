---
UID: NF:video.VideoPortSetBytesUsed
title: VideoPortSetBytesUsed function (video.h)
description: The VideoPortSetBytesUsed function is obsolete in Windows 2000 and later.
old-location: display\videoportsetbytesused.htm
tech.root: display
ms.assetid: da348cf9-5694-4e66-990e-bd07f259d97c
ms.date: 05/10/2018
keywords: ["VideoPortSetBytesUsed function"]
ms.keywords: VideoPortSetBytesUsed, VideoPortSetBytesUsed function [Display Devices], VideoPort_Functions_5a8a1a59-b9a8-4b5b-b6d8-7139ddb9b474.xml, display.videoportsetbytesused, video/VideoPortSetBytesUsed
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
targetos: Windows
req.typenames: 
f1_keywords:
 - VideoPortSetBytesUsed
 - video/VideoPortSetBytesUsed
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortSetBytesUsed
---

# VideoPortSetBytesUsed function


## -description

The <b>VideoPortSetBytesUsed</b> function is <b>obsolete</b> in Windows 2000 and later.

## -parameters

### -param HwDeviceExtension 

[in]
Pointer to the miniport driver's device extension.

### -param pDma 

[in, out]
Pointer to a DMA handle. To obtain the appropriate DMA handle, use the value in the <b>OutputBuffer</b> member of the <i>pVrp</i> parameter after <a href="/windows-hardware/drivers/ddi/video/nf-video-videoportlockpages">VideoPortLockPages</a> returns.

### -param BytesUsed 

[in]
Specifies the number of bytes written to the buffer.

## -returns

None

## -see-also

<a href="/windows-hardware/drivers/ddi/video/ns-video-_video_request_packet">VIDEO_REQUEST_PACKET</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetbytesused">VideoPortGetBytesUsed</a>