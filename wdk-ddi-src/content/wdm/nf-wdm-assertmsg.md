---
UID: NF:wdm.ASSERTMSG
title: ASSERTMSG macro (wdm.h)
description: ASSERTMSG tests an expression. If the expression is false, it breaks into the kernel debugger and sends it the specified message.
old-location: devtest\assertmsg.htm
tech.root: devtest
ms.assetid: 88c0cd30-607b-48f4-b2b6-3c21be1ce31a
ms.date: 02/23/2018
keywords: ["ASSERTMSG macro"]
ms.keywords: ASSERTMSG, ASSERTMSG function [Driver Development Tools], DebugFns_998b520e-90e6-440f-94d4-55ff0b6e102f.xml, devtest.assertmsg, ntddk/ASSERTMSG
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows 2000 and later.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ASSERTMSG
 - wdm/ASSERTMSG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - ASSERTMSG
---

# ASSERTMSG macro


## -description

<b>ASSERTMSG</b> tests an expression. If the expression is false, it breaks into the kernel debugger and sends it the specified message.

## -parameters

### -param msg

Specifies the null-delimited string to be displayed by the debugger.

### -param exp

Specifies any logical expression.

## -remarks

<b>ASSERTMSG</b> is identical to <b>ASSERT</b>, except that it sends an additional message to the debugger.

This macro will only be included in your binary if your code is compiled in a Debug configuration.

If <i>Expression</i> evaluates to <b>TRUE</b>, this routine has no effect.

If <i>Expression</i> evaluates to <b>FALSE</b>, a message is displayed in the Debugger Command window. The message contains the source-code string of <i>Expression</i>, as well as the path of the source-code file and the line number of the instruction that called the macro. In this event, <b>ASSERTMSG</b> can be ignored and the process or thread in which <b>ASSERTMSG</b> occurred can be terminated. Alternatively, the debugger can be used to analyze the situation or to edit memory. If <b>ASSERTMSG</b> is ignored, execution continues as if the <b>g (Go)</b> command was entered.

## -see-also

<a href="/previous-versions/windows/hardware/previsioning-framework/ff542107(v=vs.85)">ASSERT</a>