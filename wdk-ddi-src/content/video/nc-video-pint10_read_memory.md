---
UID: NC:video.PINT10_READ_MEMORY
title: PINT10_READ_MEMORY (video.h)
description: The Int10ReadMemory function reads a block of memory in the context of another thread and stores it in an output buffer.
old-location: display\int10readmemory.htm
tech.root: display
ms.assetid: 94b72ad0-1ace-4fde-a4a9-1078103e3d9b
ms.date: 05/10/2018
keywords: ["PINT10_READ_MEMORY callback function"]
ms.keywords: Int10ReadMemory, Int10ReadMemory callback function [Display Devices], PINT10_READ_MEMORY, PINT10_READ_MEMORY callback, VideoPort_Functions_fab5815b-1478-4d19-823f-05fd1de02b0c.xml, display.int10readmemory, video/Int10ReadMemory
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PINT10_READ_MEMORY
 - video/PINT10_READ_MEMORY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - video.h
api_name:
 - Int10ReadMemory
---

# PINT10_READ_MEMORY callback function


## -description

The <i>Int10ReadMemory </i>function reads a block of memory in the context of another thread and stores it in an output buffer.

## -parameters

### -param Context 

[in]
Pointer to a video port driver-defined context for the interface. This should be the same as the value in the <b>Context</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_int10_interface">VIDEO_PORT_INT10_INTERFACE</a> structure after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportqueryservices">VideoPortQueryServices</a> returns.

### -param Seg 

[in]
Specifies the segment address of the buffer to be read.

### -param Off 

[in]
Specifies the offset within the segment indicated by the <i>Seg</i> parameter.

### -param Buffer 

[out]
Pointer to a memory location that indicates the beginning of the output buffer.

### -param Length 

[in]
Is the length, in bytes, of the output buffer specified by the <i>Buffer</i> parameter.

## -returns

The <i>Int10ReadMemory</i> function returns NO_ERROR upon success. Otherwise it returns an appropriate error code.

## -remarks

The video port implements this function, which can be accessed through a pointer in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_int10_interface">VIDEO_PORT_INT10_INTERFACE</a> structure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_int10_interface">VIDEO_PORT_INT10_INTERFACE</a>

