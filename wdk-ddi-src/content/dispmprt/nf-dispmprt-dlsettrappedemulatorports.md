---
UID: NF:dispmprt.DlSetTrappedEmulatorPorts
title: DlSetTrappedEmulatorPorts function
author: windows-driver-content
description: 
tech.root: display
ms.assetid: 8a7ee6f8-a1cb-4a92-b6df-cb0c8679599c
ms.author: windowsdriverdev
ms.date: 04/04/2019 
ms.topic: function
f1_keywords:
 - "dispmprt/DlSetTrappedEmulatorPorts"
ms.keywords: DlSetTrappedEmulatorPorts
req.header: dispmprt.h
req.include-header:
req.target-type:
req.target-min-winverclnt: 
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- DllExport
api_location: 
- Displib.lib
- Displib.dll
api_name: 
- DlSetTrappedEmulatorPorts
product: 
- Windows
targetos: Windows

ms.custom: 19H1
---

# DlSetTrappedEmulatorPorts function


## -description

Dynamically change the list of I/O ports that are trapped when a video display monitor runs in full-screen mode on an x86-based machine.

## -parameters

### -param DeviceHandle

A handle that represents a display adapter.

### -param NumAccessRanges

Specifies the number of elements in the *AccessRange* array.

### -param AccessRange

Pointer to an array of [VIDEO_ACCESS_RANGE](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/ns-video-_video_access_range) elements.


## -returns

This function returns VP_STATUS.

## -remarks

## -see-also
