---
UID: NF:video.VideoPortReadPortBufferUshort
title: VideoPortReadPortBufferUshort function (video.h)
description: The VideoPortReadPortBufferUshort function reads a number of USHORT values from a mapped I/O port and writes them into a buffer.
old-location: display\videoportreadportbufferushort.htm
tech.root: display
ms.assetid: 3ad19dc0-f301-4367-b867-6bc714fd3d5e
ms.date: 05/10/2018
keywords: ["VideoPortReadPortBufferUshort function"]
ms.keywords: VideoPortReadPortBufferUshort, VideoPortReadPortBufferUshort function [Display Devices], VideoPort_Functions_598e11ff-25be-4b55-a86f-130100ed0972.xml, display.videoportreadportbufferushort, video/VideoPortReadPortBufferUshort
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
req.irql: See Remarks section.
targetos: Windows
req.typenames: 
f1_keywords:
 - VideoPortReadPortBufferUshort
 - video/VideoPortReadPortBufferUshort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortReadPortBufferUshort
---

# VideoPortReadPortBufferUshort function


## -description

The <b>VideoPortReadPortBufferUshort</b> function reads a number of USHORT values from a mapped I/O port and writes them into a buffer.

## -parameters

### -param Port

Pointer to the port. The given <i>Port</i> must be in a mapped I/O-space range returned by <a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.

### -param Buffer 

[out]
Pointer to a buffer into which an array of USHORT values is written.

### -param Count

Specifies the number of USHORT values to be written to the buffer.

## -returns

None

## -remarks

The buffer must be large enough to contain at least the specified number of USHORT values.

A miniport driver's <a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortReadPortBufferUshort</b>.

Callers of <b>VideoPortReadPortBufferUshort</b> can be running at any IRQL, provided that the memory pointed to by the <i>Buffer</i> parameter is resident and that pointed to by the <i>Port</i> parameter is resident, mapped device memory.

## -see-also

<a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a>



<a href="/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>