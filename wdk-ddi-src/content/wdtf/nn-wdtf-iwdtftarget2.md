---
UID: NN:wdtf.IWDTFTarget2
title: IWDTFTarget2 (wdtf.h)
description: Defines operations and properties for a testable item.
old-location: dtf\iwdtftarget2.htm
tech.root: dtf
ms.assetid: fc75c201-a3ff-44f7-ba09-8e3554b1cf27
ms.date: 04/04/2018
ms.keywords: IWDTFTarget2, IWDTFTarget2 interface [Windows Device Testing Framework], IWDTFTarget2 interface [Windows Device Testing Framework],described, Microsoft.WDTF.IWDTFTarget2, dtf.iwdtftarget2, wdtf/IWDTFTarget2
ms.topic: interface
f1_keywords:
 - "wdtf/IWDTFTarget2"
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
- IWDTFTarget2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFTarget2 interface


## -description


Defines operations and properties for a testable item.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFTarget2</b> interface inherits from <b>ITracing</b>. <b>IWDTFTarget2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
<li><a href="https://docs.microsoft.com/">Properties</a></li>
</ul>

## -members

The <b>IWDTFTarget2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtftarget2-eval">Eval</a>
</td>
<td align="left" width="63%">
Evaluates whether this target matches an SDEL statement.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtftarget2-getinterface">GetInterface</a>
</td>
<td align="left" width="63%">
Returns an action for the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtftarget2-getrelations">GetRelations</a>
</td>
<td align="left" width="63%">
Returns a collection of related targets.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-getvalue">GetValue</a>
</td>
<td align="left" width="63%">
Returns a value from the target that is associated with a specified attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtftarget2-getvaluebool">GetValueBool</a>
</td>
<td align="left" width="63%">
Returns a boolean value from the target that is associated with a specified attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtftarget2-getvaluelongnumber">GetValueLongNumber</a>
</td>
<td align="left" width="63%">
Returns a long number value from the target that is associated with a specified attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtftarget2-getvaluelongnumbers">GetValueLongNumbers</a>
</td>
<td align="left" width="63%">
Returns a collection of long number values from the target that are associated with a specified attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtftarget2-getvaluenumber">GetValueNumber</a>
</td>
<td align="left" width="63%">
Returns a number value from the target that is associated with a specified attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtftarget2-getvaluenumbers">GetValueNumbers</a>
</td>
<td align="left" width="63%">
Returns a collection of number values from the target that are associated with a specified attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtftarget2-getvaluestring">GetValueString</a>
</td>
<td align="left" width="63%">
Returns a string value from the target that is associated with a specified attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtftarget2-getvaluestrings">GetValueStrings</a>
</td>
<td align="left" width="63%">
Returns a collection of string values from the target that are associated with a specified attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtftarget2-hascontext">HasContext</a>
</td>
<td align="left" width="63%">
Determines whether a given context exists for the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtftarget2-hasinterface">HasInterface</a>
</td>
<td align="left" width="63%">
Determines whether the target supports a given interface.

</td>
</tr>
</table> 
<h3><a id="properties"></a>Properties</h3>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFTarget2</b> interface has these properties.
<table class="members" id="memberListProperties">
<tr>
<th align="left" width="27%">Property</th>
<th align="left" width="10%">Access type</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtftarget2-put_context">Context</a>


</td>
<td align="left" width="10%">
Read/write

</td>
<td align="left" width="63%">
Gets and sets a name-value pair that represents user data for the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtftarget2-get_type">Type</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets a value that identifies the depot that the target comes from.

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


## -remarks



The <b>IWDTFTarget2</b> interface abstracts the notion of a testable item, 
which is the central focus of the WDTF object model.
You can retrieve instances of the <b>IWDTFTarget2</b> interface only 
through other interfaces (such as the 
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nn-wdtf-iwdtfdevicedepot2">IWDTFDeviceDepot2</a> interface or
the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nn-wdtf-iwdtfsystemdepot2">IWDTFSystemDepot2</a> interface). 

The lifetime of a target is tied to its creator; that is, if you retrieve a target 
from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtf2-get_devicedepot">DeviceDepot</a> property, 
the target will exist as long as the <b>DeviceDepot</b> 
property exists.

You cannot copy an instance of the <b>IWDTFTarget2</b> interface. 
Even if you add a target to a collection, you really just add a reference to the same instance.

<b>Implementation Details</b>

ProgID: (Use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">IWDTF</a> 
aggregation interface to instantiate)

TraceLevel Path: HKCR\WDTF.Target.1\

<div class="alert"><b>Note</b>  The implementation of this interface is not thread-safe.</div>
<div> </div>


