---
UID: NN:wdtf.IWDTFSystemDepot2
title: IWDTFSystemDepot2 (wdtf.h)
description: Defines operations and properties for the SystemDepot - the object that represents the local computer.
old-location: dtf\iwdtfsystemdepot2.htm
tech.root: dtf
ms.assetid: 7e6e5d35-66c3-4f69-8ac0-0c1100baa5c6
ms.date: 04/04/2018
ms.keywords: IWDTFSystemDepot2, IWDTFSystemDepot2 interface [Windows Device Testing Framework], IWDTFSystemDepot2 interface [Windows Device Testing Framework],described, Microsoft.WDTF.IWDTFSystemDepot2, dtf.iwdtfsystemdepot2, wdtf/IWDTFSystemDepot2
ms.topic: interface
req.header: wdtf.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTF.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTF.Interop.metadata_dll
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
- WDTF.Interop.metadata_dll.dll
api_name:
- IWDTFSystemDepot2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFSystemDepot2 interface


## -description


Defines operations and properties for the SystemDepot - the object that represents the 
local computer.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFSystemDepot2</b> interface inherits from <b>ITracing</b>. <b>IWDTFSystemDepot2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
<li><a href="https://docs.microsoft.com/">Properties</a></li>
</ul>

## -members

The <b>IWDTFSystemDepot2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtfdevicedepot2-query">Query</a>
</td>
<td align="left" width="63%">
Returns a subset of the devices in the SystemDepot.

</td>
</tr>
</table> 
<h3><a id="properties"></a>Properties</h3>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFSystemDepot2</b> interface has these properties.
<table class="members" id="memberListProperties">
<tr>
<th align="left" width="27%">Property</th>
<th align="left" width="10%">Access type</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/hh406342(v=vs.85)">Count</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the number of devices that are currently provided by the SystemDepot.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtfnumbers2-get_item">Item</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets an individual device in the SystemDepot.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtfsystemdepot2-get_thissystem">ThisSystem</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nn-wdtf-iwdtftarget2">IWDTFTarget2</a> value that represents the local computer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtfdevicedepot2-get_wdtf">WDTF</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the main WDTF aggregation object.

</td>
</tr>
</table> 

