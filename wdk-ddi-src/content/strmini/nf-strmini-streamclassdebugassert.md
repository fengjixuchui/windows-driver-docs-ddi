---
UID: NF:strmini.StreamClassDebugAssert
title: StreamClassDebugAssert function (strmini.h)
description: This function is obsolete.
old-location: stream\streamclassdebugassert.htm
tech.root: stream
ms.assetid: df9b3231-4c43-4d4b-b128-e8d6a9f21b17
ms.date: 06/02/2020
keywords: ["StreamClassDebugAssert function"]
ms.keywords: StreamClassDebugAssert, StreamClassDebugAssert routine [Streaming Media Devices], strclass-routines_6f9302e6-592f-4097-830c-83b05a54d335.xml, stream.streamclassdebugassert, strmini/StreamClassDebugAssert
f1_keywords:
 - "strmini/StreamClassDebugAssert"
 - "StreamClassDebugAssert"
req.header: strmini.h
req.include-header: Strmini.h
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
req.lib: Stream.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Stream.lib
- Stream.dll
api_name:
- StreamClassDebugAssert
targetos: Windows
req.typenames: 
---

# StreamClassDebugAssert function

## -description

> [!NOTE]
> This function is obsolete.
>
> Checked builds were available on older versions of Windows, before Windows 10 version 1803. Use tools such as Driver Verifier and GFlags to check driver code in later versions of Windows.

## -parameters

### -param File [in]

Pointer to a NULL-terminated string containing the file name in which the assert occurred.

### -param Line [in]

Specifies the line number of the assert.

### -param AssertText [in]

Pointer to a NULL-terminated string containing text to be printed in the debug message.

### -param AssertValue [in]

Specifies a value to be printed in the debug message.

## -returns

None

## -remarks

## -see-also
