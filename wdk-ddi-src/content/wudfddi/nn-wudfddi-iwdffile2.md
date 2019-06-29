---
UID: NN:wudfddi.IWDFFile2
title: IWDFFile2 (wudfddi.h)
description: Drivers obtain the IWDFFile2 interface by calling IWDFFile::QueryInterface.
old-location: wdf\iwdffile2.htm
tech.root: wdf
ms.assetid: 49a3defc-d86c-4d70-8c1c-a5abbadda013
ms.date: 02/26/2018
ms.keywords: IWDFFile2, IWDFFile2 interface, IWDFFile2 interface,described, UMDFFileObjectRef_991af5dd-c654-4afe-9072-0efeb7ab4d57.xml, umdf.iwdffile2, wdf.iwdffile2, wudfddi/IWDFFile2
ms.topic: interface
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
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
- IWDFFile2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFFile2 interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

Drivers obtain the <b>IWDFFile2</b> interface by calling <b>IWDFFile::QueryInterface</b>.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFFile2</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdffile">IWDFFile</a>. <b>IWDFFile2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFFile2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdffile2-getrelatedfileobject">IWDFFile2::GetRelatedFileObject</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdffile2-getrelatedfileobject">GetRelatedFileObject</a> method retrieves the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdffile">IWDFFile</a> interface of a <i>related file object</i>, which is a file object that has a technology-specific relationship with another file object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdffile2-retrievecountedfilename">IWDFFile2::RetrieveCountedFileName</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdffile2-retrievecountedfilename">RetrieveCountedFileName</a> method retrieves the full counted file name for a file that is associated with a device. 

</td>
</tr>
</table> 

