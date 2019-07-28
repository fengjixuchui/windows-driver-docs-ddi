---
UID: NN:wia_lh.IWiaImageFilter
title: IWiaImageFilter (wia_lh.h)
description: The IWiaImageFilter interface is an extension interface implemented by image processing filter developers and called by Microsoft Windows Image Acquisition (WIA).
old-location: image\iwiaimagefilter_interface.htm
tech.root: image
ms.assetid: de74898b-ac04-468d-874d-7ca281e22a86
ms.date: 05/03/2018
ms.keywords: IWiaErrorHandler_3922a578-25ee-448c-a0db-c339711ad2cb.xml, IWiaImageFilter, IWiaImageFilter interface [Imaging Devices], IWiaImageFilter interface [Imaging Devices],described, image.iwiaimagefilter_interface, wia_lh/IWiaImageFilter
ms.topic: interface
f1_keywords:
 - "wia_lh/IWiaImageFilter"
req.header: wia_lh.h
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
- wia_lh.h
api_name:
- IWiaImageFilter
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaImageFilter interface


## -description


The <b>IWiaImageFilter</b> interface is an extension interface implemented by image processing filter developers and called by Microsoft Windows Image Acquisition (WIA).


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWiaImageFilter</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IWiaImageFilter</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWiaImageFilter</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wia_lh/nf-wia_lh-iwiaimagefilter-filterpreviewimage">IWiaImageFilter::FilterPreviewImage</a>
</td>
<td align="left" width="63%">
The <b>IWiaImageFilter::FilterPreviewImage</b> method is called by the WIA Preview component, when an application calls the <b>IWiaPreview::UpdatePreview</b> method.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wia_lh/nf-wia_lh-iwiaimagefilter-initializefilter">IWiaImageFilter::InitializeFilter</a>
</td>
<td align="left" width="63%">
The <b>IWiaImageFilter::InitializeFilter</b> method stores the references to <i>pWiaItem2</i> and <i>pWiaTransferCallback</i> parameters passed into the method.

</td>
</tr>
</table> 

