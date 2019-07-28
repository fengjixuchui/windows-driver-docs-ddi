---
UID: NN:filterpipeline.IPrintPipelinePropertyBag
title: IPrintPipelinePropertyBag (filterpipeline.h)
description: The IPrintPipelinePropertyBag interface is implemented by the PrintFilterPipelineSvc service and is made available to filters through methods in the IPrintPipelineFilter interface. IprintPipelinePropertyBag inherits from the IUnknown interface.
old-location: print\iprintpipelinepropertybag.htm
tech.root: print
ms.assetid: 3997291f-0af3-4fa8-8d36-20ff36551f42
ms.date: 04/20/2018
ms.keywords: IPrintPipelinePropertyBag, IPrintPipelinePropertyBag interface [Print Devices], IPrintPipelinePropertyBag interface [Print Devices],described, filterpipeline/IPrintPipelinePropertyBag, filterpipeline_e103ac79-2365-4fb3-be40-d00986bba793.xml, print.iprintpipelinepropertybag
ms.topic: interface
f1_keywords:
 - "filterpipeline/IPrintPipelinePropertyBag"
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
- IPrintPipelinePropertyBag
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintPipelinePropertyBag interface


## -description


The <code>IPrintPipelinePropertyBag</code> interface is implemented by the PrintFilterPipelineSvc service and is made available to filters through methods in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nn-filterpipeline-iprintpipelinefilter">IPrintPipelineFilter</a> interface. <code>IprintPipelinePropertyBag</code> inherits from the <b>IUnknown</b> interface.

The properties of the property bag are described in <a href="https://docs.microsoft.com/windows-hardware/drivers/print/print-pipeline-property-bag">Print Pipeline Property Bag</a>.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintPipelinePropertyBag</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrintPipelinePropertyBag</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintPipelinePropertyBag</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-iprintpipelinepropertybag-addproperty">IPrintPipelinePropertyBag::AddProperty</a>
</td>
<td align="left" width="63%">
The <code>AddProperty</code> method adds a property to a property bag.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-iprintpipelinepropertybag-deleteproperty">IPrintPipelinePropertyBag::DeleteProperty</a>
</td>
<td align="left" width="63%">
The <code>DeleteProperty</code> method deletes a property from a property bag.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-iprintpipelinepropertybag-getproperty">IPrintPipelinePropertyBag::GetProperty</a>
</td>
<td align="left" width="63%">
The <code>GetProperty</code> method gets a property from a property bag.

</td>
</tr>
</table> 

