---
UID: NN:wudfddi.IWDFUnifiedPropertyStore
title: IWDFUnifiedPropertyStore (wudfddi.h)
description: The IWDFUnifiedPropertyStore interface exposes a unified property store.
old-location: wdf\iwdfunifiedpropertystore.htm
tech.root: wdf
ms.assetid: F039450D-3B66-4891-9078-7058E889C2F0
ms.date: 02/26/2018
ms.keywords: IWDFUnifiedPropertyStore, IWDFUnifiedPropertyStore interface, IWDFUnifiedPropertyStore interface,described, umdf.iwdfunifiedpropertystore, wdf.iwdfunifiedpropertystore, wudfddi/IWDFUnifiedPropertyStore
ms.topic: interface
f1_keywords:
 - "wudfddi/IWDFUnifiedPropertyStore"
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFUnifiedPropertyStore
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFUnifiedPropertyStore interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFUnifiedPropertyStore</b> interface exposes a unified property store.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFUnifiedPropertyStore</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IWDFUnifiedPropertyStore</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFUnifiedPropertyStore</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfunifiedpropertystore-getpropertydata">GetPropertyData</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfunifiedpropertystore-getpropertydata">GetPropertyData</a> method retrieves the current setting for a device property.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfunifiedpropertystore-setpropertydata">SetPropertyData</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfunifiedpropertystore-setpropertydata">SetPropertyData</a> method modifies the current setting of a device property.

</td>
</tr>
</table> 


## -remarks



Drivers can use the  <b>IWDFUnifiedPropertyStore</b> interface to access device properties that are defined as part of the unified device property model.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfunifiedpropertystorefactory">IWDFUnifiedPropertyStoreFactory</a>
 

 

