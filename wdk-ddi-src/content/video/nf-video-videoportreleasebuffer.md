---
UID: NF:video.VideoPortReleaseBuffer
title: VideoPortReleaseBuffer function (video.h)
description: The VideoPortReleaseBuffer function is obsolete in Windows 2000 and later. In its place, video miniport drivers should instead use VideoPortFreePool. VideoPortReleaseBuffer deallocates a block of paged pool memory.
old-location: display\videoportreleasebuffer.htm
tech.root: display
ms.assetid: 627f43e7-1561-4822-b2b6-a49b54550bf5
ms.date: 05/10/2018
keywords: ["VideoPortReleaseBuffer function"]
ms.keywords: VideoPortReleaseBuffer, VideoPortReleaseBuffer function [Display Devices], VideoPort_Functions_908af223-2ee5-4e86-b5ab-47f7f3cc459b.xml, display.videoportreleasebuffer, video/VideoPortReleaseBuffer
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - VideoPortReleaseBuffer
 - video/VideoPortReleaseBuffer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortReleaseBuffer
---

# VideoPortReleaseBuffer function


## -description

The <b>VideoPortReleaseBuffer</b> function is <b>obsolete</b> in Windows 2000 and later. In its place, video miniport drivers should instead use <a href="/windows-hardware/drivers/ddi/video/nf-video-videoportfreepool">VideoPortFreePool</a>. 

<b>VideoPortReleaseBuffer</b> deallocates a block of paged pool memory.

## -parameters

### -param HwDeviceExtension 

[in]
Pointer to the miniport driver's device extension.

### -param Buffer 

[in]
Specifies the address of the block of pool memory being deallocated.

## -returns

None

## -remarks

This function releases memory allocated by <a href="/windows-hardware/drivers/ddi/video/nf-video-videoportallocatebuffer">VideoPortAllocateBuffer</a>. A miniport driver must not access the memory block to which <i>Buffer</i> points after it has been freed.

## -see-also

<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportallocatebuffer">VideoPortAllocateBuffer</a>