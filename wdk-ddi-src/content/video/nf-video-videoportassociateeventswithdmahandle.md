---
UID: NF:video.VideoPortAssociateEventsWithDmaHandle
title: VideoPortAssociateEventsWithDmaHandle function (video.h)
description: The VideoPortAssociateEventsWithDmaHandle function is obsolete in Windows 2000 and later.VideoPortAssociateEventsWithDmaHandle associates an event, which is shared by the video display driver and the video miniport driver, with a DMA handle.
old-location: display\videoportassociateeventswithdmahandle.htm
tech.root: display
ms.assetid: d8a64a06-41b9-429b-a5ac-6de4996c702b
ms.date: 05/10/2018
keywords: ["VideoPortAssociateEventsWithDmaHandle function"]
ms.keywords: VideoPortAssociateEventsWithDmaHandle, VideoPortAssociateEventsWithDmaHandle function [Display Devices], VideoPort_Functions_0b61cb97-6bee-4882-83c9-1a56b8c2807b.xml, display.videoportassociateeventswithdmahandle, video/VideoPortAssociateEventsWithDmaHandle
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
 - VideoPortAssociateEventsWithDmaHandle
 - video/VideoPortAssociateEventsWithDmaHandle
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortAssociateEventsWithDmaHandle
---

# VideoPortAssociateEventsWithDmaHandle function


## -description

The <b>VideoPortAssociateEventsWithDmaHandle</b> function is <b>obsolete</b> in Windows 2000 and later.

<b>VideoPortAssociateEventsWithDmaHandle</b> associates an event, which is shared by the video display driver and the video miniport driver, with a DMA handle.

## -parameters

### -param HwDeviceExtension 

[in]
Pointer to the miniport driver's device extension.

### -param pVrp 

[in, out]
Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_request_packet">VIDEO_REQUEST_PACKET</a>.

### -param MappedUserEvent 

[in]
Is reserved for system use.

### -param DisplayDriverEvent 

[in]
Is reserved for system use.

## -returns

<b>VideoPortAssociateEventsWithDmaHandle</b> always returns <b>NULL</b>.

## -remarks

See <a href="https://docs.microsoft.com/windows-hardware/drivers/display/bus-master-dma-in-video-miniport-drivers">Bus-Master DMA in Video Miniport Drivers</a> for information about packet-based and common-buffer DMA transfers.

