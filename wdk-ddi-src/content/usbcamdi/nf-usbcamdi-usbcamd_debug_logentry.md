---
UID: NF:usbcamdi.USBCAMD_Debug_LogEntry
title: USBCAMD_Debug_LogEntry function (usbcamdi.h)
description: The USBCAMD_Debug_LogEntry function is called by the camera minidriver to log debugging information to a file.
old-location: stream\usbcamd_debug_logentry.htm
tech.root: stream
ms.assetid: a718cf3e-8359-4560-a88e-dd7789b61be6
ms.date: 11/18/2019
ms.keywords: USBCAMD_Debug_LogEntry, USBCAMD_Debug_LogEntry function [Streaming Media Devices], stream.usbcamd_debug_logentry, usbcamdi/USBCAMD_Debug_LogEntry, usbcmdpr_6f6f6419-d845-4488-bd8d-70efa67357fa.xml
ms.topic: function
f1_keywords:
 - "usbcamdi/USBCAMD_Debug_LogEntry"
req.header: usbcamdi.h
req.include-header: Usbcamdi.h
req.target-type: Desktop
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
req.lib: Usbcamd2.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- usbcamd2.lib
- usbcamd2.dll
api_name:
- USBCAMD_Debug_LogEntry
product:
- Windows
targetos: Windows
req.typenames: 
---

# USBCAMD_Debug_LogEntry function

## -description

The **USBCAMD_Debug_LogEntry** function is called by the camera minidriver to log debugging information to a file.

## -parameters

### -param Name [in]

Pointer to a **NULL**-terminated string containing the name of the file to write the log entry to.

### -param Info1 [in]

Specifies the first information value to be written to the log file.

### -param Info2 [in]

Specifies the second information value to be written to the log file.

### -param Info3 [in]

Specifies the third information value to be written to the log file.

## -remarks

The original USBCAMD does not call **USBCAMD_Debug_LogEntry**.
