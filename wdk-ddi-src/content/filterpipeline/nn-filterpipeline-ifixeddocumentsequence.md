---
UID: NN:filterpipeline.IFixedDocumentSequence
title: IFixedDocumentSequence (filterpipeline.h)
description: The IFixedDocumentSequence interface represents the fixed document sequence for an XPS document.
old-location: print\ifixeddocumentsequence.htm
tech.root: print
ms.assetid: 8919e2d1-0c39-46b6-b06e-83fe61f67751
ms.date: 04/20/2018
ms.keywords: IFixedDocumentSequence, IFixedDocumentSequence interface [Print Devices], IFixedDocumentSequence interface [Print Devices],described, filterpipeline/IFixedDocumentSequence, filterpipeline_ed0de3e6-e4c7-43e6-a6cf-c16d3a086838.xml, print.ifixeddocumentsequence
ms.topic: interface
f1_keywords:
 - "filterpipeline/IFixedDocumentSequence"
req.header: filterpipeline.h
req.include-header: Filterpipeline.h
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
- filterpipeline.h
api_name:
- IFixedDocumentSequence
product:
- Windows
targetos: Windows
req.typenames: 
---

# IFixedDocumentSequence interface


## -description


The <b>IFixedDocumentSequence</b> interface represents the fixed document sequence for an XPS document.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IFixedDocumentSequence</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IFixedDocumentSequence</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IFixedDocumentSequence</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ifixeddocumentsequence-getprintticket">IFixedDocumentSequence::GetPrintTicket</a>
</td>
<td align="left" width="63%">
The <b>GetPrintTicket</b> method gets the print ticket object for the fixed document sequence.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ifixeddocumentsequence-geturi">IFixedDocumentSequence::GetUri</a>
</td>
<td align="left" width="63%">
The <b>GetUri</b> method gets the URI of the fixed document sequence.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ifixeddocumentsequence-setprintticket">IFixedDocumentSequence::SetPrintTicket</a>
</td>
<td align="left" width="63%">
The <b>SetPrintTicket</b> method inserts a print ticket into the fixed document sequence.

</td>
</tr>
</table> 

