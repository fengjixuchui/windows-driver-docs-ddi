---
UID: NN:filterpipeline.IXpsPartIterator
title: IXpsPartIterator (filterpipeline.h)
description: The IXpsPartIterator interface is an iterator for XPS parts.
old-location: print\ixpspartiterator.htm
tech.root: print
ms.assetid: 6fd51647-e7e4-4c9a-ae87-00eb3e1d3fbb
ms.date: 04/20/2018
ms.keywords: IXpsPartIterator, IXpsPartIterator interface [Print Devices], IXpsPartIterator interface [Print Devices],described, filterpipeline/IXpsPartIterator, filterpipeline_75476300-7fcc-46a5-8a48-abde1dcd5e36.xml, print.ixpspartiterator
ms.topic: interface
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
- IXpsPartIterator
product:
- Windows
targetos: Windows
req.typenames: 
---

# IXpsPartIterator interface


## -description


The <code>IXpsPartIterator</code> interface is an iterator for XPS parts.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IXpsPartIterator</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IXpsPartIterator</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IXpsPartIterator</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ixpspartiterator-current">IXpsPartIterator::Current</a>
</td>
<td align="left" width="63%">
The <code>Current</code> method provides the current URI and part.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ixpspartiterator-isdone">IXpsPartIterator::IsDone</a>
</td>
<td align="left" width="63%">
The <code>IsDone</code> method determines whether the iterator has finished  the iteration.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ixpspartiterator-next">IXpsPartIterator::Next</a>
</td>
<td align="left" width="63%">
The <code>Next</code> method advances the iterator to the next part.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ixpspartiterator-reset">IXpsPartIterator::Reset</a>
</td>
<td align="left" width="63%">
The <code>Reset</code> method sets the iterator to the first element.

</td>
</tr>
</table> 

