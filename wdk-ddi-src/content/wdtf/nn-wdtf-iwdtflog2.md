---
UID: NN:wdtf.IWDTFLOG2
title: IWDTFLOG2 (wdtf.h)
description: Defines operations that enable the test case author to add to the WDTF test log.
old-location: dtf\iwdtflog2.htm
tech.root: dtf
ms.assetid: e09d0c3d-28a0-4c8d-ac70-9575968cbea1
ms.date: 04/04/2018
ms.keywords: IWDTFLOG2, IWDTFLOG2 interface [Windows Device Testing Framework], IWDTFLOG2 interface [Windows Device Testing Framework],described, Microsoft.WDTF.IWDTFLOG2, dtf.iwdtflog2, wdtf/IWDTFLOG2
ms.topic: interface
f1_keywords:
 - "wdtf/IWDTFLOG2"
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
- IWDTFLOG2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFLOG2 interface


## -description


Defines operations that enable the test case author to add to the WDTF test log.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFLOG2</b> interface inherits from the <a href="ebbff4bc-36b2-4861-9efa-ffa45e013eb5">IDispatch</a> interface. <b>IWDTFLOG2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDTFLOG2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtflog2-endtestcase">EndTestCase</a>
</td>
<td align="left" width="63%">
Marks the end of a test case.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtflog2-outputerror">OutputError</a>
</td>
<td align="left" width="63%">
Writes an error entry to the test case log.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtflog2-outputinfo">OutputInfo</a>
</td>
<td align="left" width="63%">
Writes an informational entry to the test case log.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtflog2-starttestcase">StartTestCase</a>
</td>
<td align="left" width="63%">
Marks the start of a test case.

</td>
</tr>
</table> 


## -remarks



You access the logging interface from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtf2-get_log">IWDTF2::Log</a> property.



