---
UID: NF:strmini.StreamClassDebugPrint
title: StreamClassDebugPrint function (strmini.h)
description: In a checked build environment, the minidriver can use the StreamClassDebugPrint routine to print debug messages to the application window and to the Debugger Command window.
old-location: stream\streamclassdebugprint.htm
tech.root: stream
ms.assetid: a8b7efd2-7773-44dc-92de-85b03c31ada8
ms.date: 04/23/2018
ms.keywords: StreamClassDebugPrint, StreamClassDebugPrint routine [Streaming Media Devices], strclass-routines_858a2dd4-ee74-44de-9293-05bd804c315d.xml, stream.streamclassdebugprint, strmini/StreamClassDebugPrint
ms.topic: function
f1_keywords:
 - "strmini/StreamClassDebugPrint"
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
- StreamClassDebugPrint
product:
- Windows
targetos: Windows
req.typenames: 
---

# StreamClassDebugPrint function


## -description


In a checked build environment, the minidriver can use the <b>StreamClassDebugPrint</b> routine to print debug messages to the application window and to the Debugger Command window.


## -parameters




### -param DebugPrintLevel [in]

Specifies an enumeration of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ne-strmini-stream_debug_level">STREAM_DEBUG_LEVEL</a>. The debugger prints messages if this parameter is less than or equal to the <i>StreamDebug</i> variable in <i>stream.sys</i> symbols.


### -param DebugMessage [in]

Points to a <b>NULL</b>-terminated string containing the message to print to the application window and to the Debugger Command window.


### -param param






#### - arguments

Specifies a variable argument list containing optional arguments for the format string, as in <b>printf</b>.


## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/stream-class-debugging">Stream Class Debugging</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-dbgprint">DbgPrint</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassdebugassert">StreamClassDebugAssert</a>
 

 

