---
UID: NN:printerextension.IPrinterExtensionEvent
title: IPrinterExtensionEvent (printerextension.h)
description: The IPrinterExtensionEvent interface represents the event delegate implemented by desktop printer extensions for activation.
old-location: print\iprinterextensionevent_interface.htm
tech.root: print
ms.assetid: A0F4DB51-D68E-4516-833A-7E984247796B
ms.date: 04/20/2018
ms.keywords: IPrinterExtensionEvent, IPrinterExtensionEvent interface [Print Devices], IPrinterExtensionEvent interface [Print Devices],described, print.iprinterextensionevent_interface, printerextension/IPrinterExtensionEvent
ms.topic: interface
f1_keywords:
 - "printerextension/IPrinterExtensionEvent"
req.header: printerextension.h
req.include-header: 
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
- printerextension.h
api_name:
- IPrinterExtensionEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterExtensionEvent interface


## -description


The IPrinterExtensionEvent interface represents the event delegate implemented by desktop printer extensions for activation.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterExtensionEvent</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrinterExtensionEvent</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrinterExtensionEvent</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterextensionevent-ondriverevent">OnDriverEvent</a>
</td>
<td align="left" width="63%">
Called when a driver event occurs.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterextensionevent-onprinterqueuesenumerated">OnPrinterQueuesEnumerated</a>
</td>
<td align="left" width="63%">
Called when printer queues are enumerated.

</td>
</tr>
</table> 

