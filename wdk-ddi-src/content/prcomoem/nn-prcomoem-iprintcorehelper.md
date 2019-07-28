---
UID: NN:prcomoem.IPrintCoreHelper
title: IPrintCoreHelper (prcomoem.h)
description: This section describes the methods that are defined for the IPrintCoreHelper COM interface.
old-location: print\iprintcorehelper_interface.htm
tech.root: print
ms.assetid: db13410f-e4cb-4077-bb4b-7963e97b435c
ms.date: 04/20/2018
ms.keywords: IPrintCoreHelper, IPrintCoreHelper interface [Print Devices], IPrintCoreHelper interface [Print Devices],described, prcomoem/IPrintCoreHelper, print.iprintcorehelper_interface, print_unidrv-pscript_allplugins_9609acef-24e8-4802-9c70-196fef2b011f.xml
ms.topic: interface
f1_keywords:
 - "prcomoem/IPrintCoreHelper"
req.header: prcomoem.h
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
- prcomoem.h
api_name:
- IPrintCoreHelper
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCoreHelper interface


## -description


This section describes the methods that are defined for the <b>IPrintCoreHelper</b> COM interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintCoreHelper</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrintCoreHelper</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintCoreHelper</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelper-createinstanceofmsxmlobject">CreateInstanceOfMSXMLObject</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelper::CreateInstanceOfMSXMLObject</b> method creates an instance of an MSXML 6.0 object by using the correct MSXML DLL. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelper-enumconstrainedoptions">EnumConstrainedOptions</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelper::EnumConstrainedOptions</b> method provides a list of all of the options that are constrained in a particular feature, based on current settings.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelper-enumfeatures">EnumFeatures</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelper::EnumFeatures</b> method gets a list of all available features, including synthesized and core driver-implement features.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelper-enumoptions">EnumOptions</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelper::EnumOptions</b> method gets a list of available options for the given feature. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelper-getfontsubstitution">GetFontSubstitution</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelper::GetFontSubstitution</b> method indicates which device font, if any, is used as a substitution font for a specified TrueType font.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschemafeature-getoption">GetOption</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelper::GetOption</b> method gets a specified option for a given feature.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelper-setfontsubstitution">SetFontSubstitution</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelper::SetFontSubstitution</b> method specifies the device font to print in place of a given TrueType font. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelper-setoptions">SetOptions</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelper::SetOptions</b> method sets multiple feature-option pairs at the same time.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintcorehelper-whyconstrained">WhyConstrained</a>
</td>
<td align="left" width="63%">
The <b>IPrintCoreHelper::WhyConstrained</b> method provides a list of options that are constraining the specified feature-option pair in the current configuration.

</td>
</tr>
</table> 

