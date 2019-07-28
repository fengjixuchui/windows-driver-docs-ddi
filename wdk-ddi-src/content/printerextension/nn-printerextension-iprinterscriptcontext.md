---
UID: NN:printerextension.IPrinterScriptContext
title: IPrinterScriptContext (printerextension.h)
description: Passed to all third-party constraints JavaScript functions, and provides access to relevant objects.
old-location: print\iprinterscriptcontext.htm
tech.root: print
ms.assetid: B44B47EA-6848-430E-9C10-F6DD460C2304
ms.date: 04/20/2018
ms.keywords: IPrinterScriptContext, IPrinterScriptContext interface [Print Devices], IPrinterScriptContext interface [Print Devices],described, print.iprinterscriptcontext, printerextension/IPrinterScriptContext
ms.topic: interface
f1_keywords:
 - "printerextension/IPrinterScriptContext"
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- Printerextension.h
api_name:
- IPrinterScriptContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterScriptContext interface


## -description


Passed to all third-party constraints JavaScript functions, and provides access to relevant objects.
<ul>
<li><a href="https://docs.microsoft.com/">Properties</a></li>
</ul><h3><a id="properties"></a>Properties</h3>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterScriptContext</b> interface has these properties.
<table class="members" id="memberListProperties">
<tr>
<th align="left" width="27%">Property</th>
<th align="left" width="10%">Access type</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterextensioncontext-get_driverproperties">DriverProperties</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Provides access to the driver property bag, if the property bag is present.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterscriptcontext-get_queueproperties">QueueProperties</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Provides access to the queue property bag, if the property bag is present.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterextensioncontext-get_userproperties">UserProperties</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Provides access to the user property bag, if the property bag is present.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/print/v4-driver-property-bags">V4 Printer Driver Property Bags</a>
 

 

