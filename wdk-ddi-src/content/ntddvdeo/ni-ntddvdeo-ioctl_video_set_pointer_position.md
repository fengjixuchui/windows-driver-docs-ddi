---
UID: NI:ntddvdeo.IOCTL_VIDEO_SET_POINTER_POSITION
title: IOCTL_VIDEO_SET_POINTER_POSITION (ntddvdeo.h)
description: Sets the pointer position. Support for this modal request is optional. A supporting miniport driver should have already processed an enable-pointer request before processing this request.
old-location: display\ioctl_video_set_pointer_position.htm
tech.root: display
ms.assetid: de581a49-da6d-410b-82be-28cc1eccfde4
ms.date: 05/10/2018
ms.keywords: IOCTL_VIDEO_SET_POINTER_POSITION, IOCTL_VIDEO_SET_POINTER_POSITION control, IOCTL_VIDEO_SET_POINTER_POSITION control code [Display Devices], Video_IOCTLs_cc9ab1b6-f2be-4dab-b657-f686bc0af329.xml, display.ioctl_video_set_pointer_position, ntddvdeo/IOCTL_VIDEO_SET_POINTER_POSITION
ms.topic: ioctl
f1_keywords:
 - "ntddvdeo/IOCTL_VIDEO_SET_POINTER_POSITION"
req.header: ntddvdeo.h
req.include-header: 
req.target-type: Windows
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
- HeaderDef
api_location:
- Ntddvdeo.h
api_name:
- IOCTL_VIDEO_SET_POINTER_POSITION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_VIDEO_SET_POINTER_POSITION IOCTL


## -description



Sets the pointer position. Support for this modal request is optional. A supporting miniport driver should have already processed an enable-pointer request before processing this request.




## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains the VIDEO_POINTER_POSITION structure to be set.


### -input-buffer-length








### -output-buffer

None


### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

The miniport driver does not set the <b>Information</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/ns-video-_status_block">STATUS_BLOCK</a> structure.

