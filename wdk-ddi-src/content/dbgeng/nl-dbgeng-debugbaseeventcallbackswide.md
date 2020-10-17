---
UID: NL:dbgeng.DebugBaseEventCallbacksWide
title: DebugBaseEventCallbacksWide (dbgeng.h)
description: The DebugBaseEventCallbacksWide class provides a base implementation of the IDebugEventCallbacksWide interface.
old-location: debugger\debugbaseeventcallbackswide.htm
tech.root: debugger
ms.assetid: 38AD8472-1BA3-42EA-99CE-E91098A5B334
ms.date: 05/03/2018
keywords: ["DebugBaseEventCallbacksWide class"]
ms.keywords: DebugBaseEventCallbacksWide, DebugBaseEventCallbacksWide class [Windows Debugging], DebugBaseEventCallbacksWide class [Windows Debugging],described, dbgeng/DebugBaseEventCallbacksWide, debugger.debugbaseeventcallbackswide
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - DebugBaseEventCallbacksWide
 - dbgeng/DebugBaseEventCallbacksWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - DebugBaseEventCallbacksWide
---

# DebugBaseEventCallbacksWide class


## -description

The <b>DebugBaseEventCallbacksWide</b> class provides a base implementation
of the <a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugeventcallbackswide">IDebugEventCallbacksWide</a> interface.  

A program can derive an event callbacks class from <b>DebugBaseEventCallbacksWide</b> and implement
only the methods needed. 

Be careful to implement <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbackswide-getinterestmask">GetInterestMask</a> appropriately.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbackswide-getinterestmask">GetInterestMask</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugeventcallbackswide">IDebugEventCallbacksWide</a>