---
UID: NN:wdtf.IWDTFStrings2
title: IWDTFStrings2 (wdtf.h)
description: Defines operations and properties for a collection of strings.
old-location: dtf\iwdtfstrings2.htm
tech.root: dtf
ms.assetid: ea7ebda9-9588-4c72-bac6-2bae1f80538e
ms.date: 04/04/2018
ms.keywords: IWDTFStrings2, IWDTFStrings2 interface [Windows Device Testing Framework], IWDTFStrings2 interface [Windows Device Testing Framework],described, Microsoft.WDTF.IWDTFStrings2, dtf.iwdtfstrings2, wdtf/IWDTFStrings2
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
- IWDTFStrings2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFStrings2 interface


## -description


Defines operations and properties for a collection of strings.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFStrings2</b> interface inherits from <b>ITracing</b>. <b>IWDTFStrings2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
<li><a href="https://docs.microsoft.com/">Properties</a></li>
</ul>

## -members

The <b>IWDTFStrings2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/test/wpt/add">Add</a>
</td>
<td align="left" width="63%">
Adds a single string to the collection.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtftargets2-remove">Remove</a>
</td>
<td align="left" width="63%">
Removes a string from the collection.

</td>
</tr>
</table> 
<h3><a id="properties"></a>Properties</h3>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFStrings2</b> interface has these properties.
<table class="members" id="memberListProperties">
<tr>
<th align="left" width="27%">Property</th>
<th align="left" width="10%">Access type</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtfstrings2-get__newenum">_NewEnum</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets a new iteration variable that the <b>For Each</b> 
loop structure implicitly uses.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/hh406342(v=vs.85)">Count</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the number of strings in this collection.

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
Gets an individual string in the collection.

</td>
</tr>
</table> 

