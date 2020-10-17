---
UID: NF:video.VideoPortReleaseSpinLock
title: VideoPortReleaseSpinLock function (video.h)
description: The VideoPortReleaseSpinLock function releases ownership of a given spin lock and restores the original IRQL at which the caller was running.
old-location: display\videoportreleasespinlock.htm
tech.root: display
ms.assetid: 8ce2006e-e66c-4b2d-8d26-2eba8d8e2864
ms.date: 03/29/2018
keywords: ["VideoPortReleaseSpinLock function"]
ms.keywords: VideoPortReleaseSpinLock, VideoPortReleaseSpinLock function [Display Devices], VideoPort_Functions_43cceda5-f5eb-4567-97f5-d53d0bf93c0b.xml, display.videoportreleasespinlock, video/VideoPortReleaseSpinLock
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
req.irql: DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
f1_keywords:
 - VideoPortReleaseSpinLock
 - video/VideoPortReleaseSpinLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortReleaseSpinLock
---

# VideoPortReleaseSpinLock function


## -description

The <b>VideoPortReleaseSpinLock</b> function releases ownership of a given spin lock and restores the original IRQL at which the caller was running.

## -parameters

### -param HwDeviceExtension 

[in] Pointer to the miniport driver's device extension.

### -param SpinLock

[in, out] Pointer to a memory location that contains the spin lock to be released.

### -param NewIrql 

[in] Specifies the IRQL to be restored.

## -returns

None

## -remarks

This call is the inverse of <a href="/previous-versions/ff570175(v=vs.85)">VideoPortAcquireSpinLock</a>. The <i>NewIrql</i> value must be the same as the value pointed to by <i>OldIrql</i> when <b>VideoPortAcquireSpinLock </b>returned.

Callers of <b>VideoPortReleaseSpinLock</b> must be running at IRQL = DISPATCH_LEVEL. On return from this routine, IRQL is restored to the <i>NewIrql</i> value.

## -see-also

<a href="/previous-versions/ff570175(v=vs.85)">VideoPortAcquireSpinLock</a>