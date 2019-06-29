---
UID: NN:filterpipeline.IPartFont
title: IPartFont (filterpipeline.h)
description: The IPartFont interface is the abstraction for fonts in a part.
old-location: print\ipartfont.htm
tech.root: print
ms.assetid: bdb1ad56-de4c-4a9b-96b6-f9faff4abf65
ms.date: 04/20/2018
ms.keywords: IPartFont, IPartFont interface [Print Devices], IPartFont interface [Print Devices],described, filterpipeline/IPartFont, filterpipeline_def05492-ca27-43bb-9ec4-273aa432536b.xml, print.ipartfont
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
- IPartFont
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPartFont interface


## -description


The <b>IPartFont</b> interface is the abstraction for fonts in a part.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPartFont</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nn-filterpipeline-ipartbase">IPartBase</a>. <b>IPartFont</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPartFont</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ipartfont-getfontproperties">IPartFont::GetFontProperties</a>
</td>
<td align="left" width="63%">
The <b>GetFontProperties</b> method gets the font properties.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ipartfont-setfontcontent">IPartFont::SetFontContent</a>
</td>
<td align="left" width="63%">
The <b>SetFontContent</b> method sets the content of the font.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-ipartfont-setfontoptions">IPartFont::SetFontOptions</a>
</td>
<td align="left" width="63%">
The <b>SetFontOptions</b> method sets the options for the font.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nn-filterpipeline-ipartbase">IPartBase</a>
 

 

