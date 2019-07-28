---
UID: NN:dbgeng.IDebugPlmClient
title: IDebugPlmClient (dbgeng.h)
description: This interface supports Process Lifecycle Management (PLM) for the debug client.
old-location: debugger\idebugplmclient.htm
tech.root: debugger
ms.assetid: 2D713354-4C93-4DC1-A3E9-7E6BC991FD08
ms.date: 05/03/2018
ms.keywords: IDebugPlmClient, IDebugPlmClient interface [Windows Debugging], IDebugPlmClient interface [Windows Debugging],described, dbgeng/IDebugPlmClient, debugger.idebugplmclient
ms.topic: interface
f1_keywords:
 - "dbgeng/IDebugPlmClient"
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
- IDebugPlmClient
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugPlmClient interface


## -description


This interface supports Process Lifecycle Management (PLM) for the debug client.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugPlmClient</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IDebugPlmClient</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugPlmClient</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugplmclient-launchplmpackagefordebugwide">LaunchPlmPackageForDebugWide</a>
</td>
<td align="left" width="63%">
Launches a suspended Process Lifecycle Management (PLM) application.

</td>
</tr>
</table> 

