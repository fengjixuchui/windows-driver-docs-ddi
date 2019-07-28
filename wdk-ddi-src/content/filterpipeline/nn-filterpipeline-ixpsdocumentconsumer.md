---
UID: NN:filterpipeline.IXpsDocumentConsumer
title: IXpsDocumentConsumer (filterpipeline.h)
description: A filter uses the IXpsDocumentConsumer interface when it generates XPS content for the pipeline to consume.
old-location: print\ixpsdocumentconsumer.htm
tech.root: print
ms.assetid: 98e603e6-2786-4bc8-ad8a-0e91b0d444d8
ms.date: 04/20/2018
ms.keywords: IXpsDocumentConsumer, IXpsDocumentConsumer interface [Print Devices], IXpsDocumentConsumer interface [Print Devices],described, filterpipeline/IXpsDocumentConsumer, filterpipeline_230eb0f6-427a-4986-b8ad-bc1d41853d67.xml, print.ixpsdocumentconsumer
ms.topic: interface
f1_keywords:
 - "filterpipeline/IXpsDocumentConsumer"
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
- IXpsDocumentConsumer
product:
- Windows
targetos: Windows
req.typenames: 
---

# IXpsDocumentConsumer interface


## -description


A filter uses the <code>IXpsDocumentConsumer</code> interface when it generates XPS content for the pipeline to consume. 
<div class="alert"><b>Note</b>    The XPS print filter pipeline does not preserve digital signatures or story fragments. You may be able to work around this by using stream filters.</div><div> </div>

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IXpsDocumentConsumer</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IXpsDocumentConsumer</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IXpsDocumentConsumer</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ixpsdocumentconsumer-closesender">IXpsDocumentConsumer::CloseSender</a>
</td>
<td align="left" width="63%">
The <code>CloseSender</code> method tells the Pipeline Manager that the filter is done sending XPS parts.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ixpsdocumentconsumer-getnewemptypart">IXpsDocumentConsumer::GetNewEmptyPart</a>
</td>
<td align="left" width="63%">
The <code>GetNewEmptyPart</code> method creates a new XPS part.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ixpsdocumentconsumer-sendfixeddocument">IXpsDocumentConsumer::SendFixedDocument</a>
</td>
<td align="left" width="63%">
The <code>SendFixedDocument</code> method sends a fixed document object to the pipeline.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ixpsdocumentconsumer-sendfixeddocumentsequence">IXpsDocumentConsumer::SendFixedDocumentSequence</a>
</td>
<td align="left" width="63%">
The <b>SendFixedDocumentSequence</b> method sends a fixed document sequence to the pipeline.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ixpsdocumentconsumer-sendfixedpage">IXpsDocumentConsumer::SendFixedPage</a>
</td>
<td align="left" width="63%">
The <code>SendFixedPage</code> method sends a fixed page of an XPS document to the pipeline.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ixpsdocumentconsumer-sendxpsdocument">IXpsDocumentConsumer::SendXpsDocument</a>
</td>
<td align="left" width="63%">
The <code>SendXpsDocument</code> method sends an XPS document to the pipeline. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ixpsdocumentconsumer-sendxpsunknown">IXpsDocumentConsumer::SendXpsUnknown</a>
</td>
<td align="left" width="63%">
The <code>SendXpsUnknown</code> method sends an XPS document part that cannot be identified to the filter pipeline.

</td>
</tr>
</table> 

