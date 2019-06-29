---
UID: NN:dbgeng.IDebugOutputCallbacks
title: IDebugOutputCallbacks (dbgeng.h)
description: IDebugOutputCallbacks interface
old-location: debugger\idebugoutputcallbacks.htm
tech.root: debugger
ms.assetid: 6b29e15c-3a9d-4d96-8b72-22064526ca75
ms.date: 05/03/2018
ms.keywords: ComCallbacks_ed6ca0bd-5599-426d-b089-18a12311eba0.xml, IDebugOutputCallbacks, IDebugOutputCallbacks interface [Windows Debugging], IDebugOutputCallbacks interface [Windows Debugging],described, dbgeng/IDebugOutputCallbacks, debugger.idebugoutputcallbacks
ms.topic: interface
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugOutputCallbacks
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugOutputCallbacks interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugOutputCallbacks</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IDebugOutputCallbacks</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugOutputCallbacks</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553183">Output</a>
</td>
<td align="left" width="63%">
This method is called by the engine to send output from the client to the <b>IDebugOutputCallbacks</b> object that is registered with the client.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugoutputcallbackswide">IDebugOutputCallbacksWide</a>
 

 

