---
UID: NN:printerextension.IPrinterExtensionManager
title: IPrinterExtensionManager (printerextension.h)
description: The IPrinterExtensionManager interface is retrieved by CoCreating the PrinterExtensionManager class.
old-location: print\iprinterextensionmanager_interface.htm
tech.root: print
ms.assetid: 918AE3F6-2AC4-42AD-9581-E87AD7E79BAD
ms.date: 04/20/2018
ms.keywords: IPrinterExtensionManager, IPrinterExtensionManager interface [Print Devices], IPrinterExtensionManager interface [Print Devices],described, print.iprinterextensionmanager_interface, printerextension/IPrinterExtensionManager
ms.topic: interface
f1_keywords:
 - "printerextension/IPrinterExtensionManager"
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
- IPrinterExtensionManager
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterExtensionManager interface


## -description


The <b>IPrinterExtensionManager</b> interface is retrieved by CoCreating the <b>PrinterExtensionManager</b> class.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterExtensionManager</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrinterExtensionManager</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrinterExtensionManager</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterextensionmanager-disableevents">DisableEvents</a>
</td>
<td align="left" width="63%">
Disallows events to be generated.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterextensionmanager-enableevents">EnableEvents</a>
</td>
<td align="left" width="63%">
The EnableEvents method allows events to be generated for the specified printer driver until  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterextensionmanager-disableevents">DisableEvents</a> is called. 

</td>
</tr>
</table> 


## -remarks



Any event sink that implements <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprinterextensionevent">IPrinterExtensionEvent</a> is connected to the associated event source, <b>IPrinterExtensionManager</b>, via the <b>IConnectionPoint</b> mechanism. You must retrieve a pointer to the <b>IConnectionPoint</b> interface by invoking <b>QueryInterface</b> on the <b>IPrinterExtensionManager</b> object.

<div class="alert"><b>Note</b>  It is mandatory to implement <b>IDispatch::Invoke</b> on the event sink that implements <b>IPrinterExtensionEvent</b>, since that is the mechanism via which events are raised. It is sufficient to provide stub implementations of the other methods on the <b>IDispatch</b> interface.</div>
<div> </div>


