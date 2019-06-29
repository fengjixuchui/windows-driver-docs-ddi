---
UID: NN:wudfddi.IObjectCleanup
title: IObjectCleanup (wudfddi.h)
description: Any driver that stores a reference-counted COM interface to a WDF object must support the IObjectCleanup interface to prevent interface leakage. Note that drivers, in general, are not required to hold references to WDF objects.
old-location: wdf\iobjectcleanup.htm
tech.root: wdf
ms.assetid: 5e465c90-3290-4c89-bf47-521280c0fe5c
ms.date: 02/26/2018
ms.keywords: IObjectCleanup, IObjectCleanup interface, IObjectCleanup interface,described, UMDFBaseObjectRef_4e434f46-a62e-4410-b8ed-663ab59c89dd.xml, umdf.iobjectcleanup, wdf.iobjectcleanup, wudfddi/IObjectCleanup
ms.topic: interface
req.header: wudfddi.h
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
- Wudfddi.h
api_name:
- IObjectCleanup
product:
- Windows
targetos: Windows
req.typenames: 
---

# IObjectCleanup interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

Any driver that stores a reference-counted COM interface to a WDF object must support the <b>IObjectCleanup</b> interface to prevent interface leakage. Note that drivers, in general, are not required to hold references to WDF objects.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IObjectCleanup</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IObjectCleanup</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IObjectCleanup</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iobjectcleanup-oncleanup">IObjectCleanup::OnCleanup</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iobjectcleanup-oncleanup">OnCleanup</a> method releases any references to a WDF object to prevent interface leakage.

</td>
</tr>
</table> 


## -remarks



The framework calls the method of the <b>IObjectCleanup</b> interface when the associated framework object is about to be released.

A driver can register the <b>IObjectCleanup</b> interface when the driver calls any method that creates a WDF object. 



