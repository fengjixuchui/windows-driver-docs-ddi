---
UID: NN:wudfddi.IWDFIoTarget2
title: IWDFIoTarget2 (wudfddi.h)
description: To obtain the IWDFIoTarget2 interface, drivers call IWDFIoTarget::QueryInterface.
old-location: wdf\iwdfiotarget2.htm
tech.root: wdf
ms.assetid: 52ce1c63-b2cf-4eda-b056-4f1f999110c5
ms.date: 02/26/2018
ms.keywords: IWDFIoTarget2, IWDFIoTarget2 interface, IWDFIoTarget2 interface,described, UMDFIoTargetObjectRef_7639fcef-e463-4500-94a0-132b63e1e564.xml, umdf.iwdfiotarget2, wdf.iwdfiotarget2, wudfddi/IWDFIoTarget2
ms.topic: interface
f1_keywords:
 - "wudfddi/IWDFIoTarget2"
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
- IWDFIoTarget2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoTarget2 interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

To obtain the <b>IWDFIoTarget2</b> interface, drivers call <b>IWDFIoTarget::QueryInterface</b>.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFIoTarget2</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfiotarget">IWDFIoTarget</a>. <b>IWDFIoTarget2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFIoTarget2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiotarget2-formatrequestforflush">IWDFIoTarget2::FormatRequestForFlush</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiotarget2-formatrequestforflush">FormatRequestForFlush</a> method builds an I/O request for a flush operation but does not send the request to an I/O target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiotarget2-formatrequestforqueryinformation">IWDFIoTarget2::FormatRequestForQueryInformation</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiotarget2-formatrequestforqueryinformation">FormatRequestForQueryInformation</a> method formats an I/O request to obtain information about a file, but it does not send the request to an I/O target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiotarget2-formatrequestforsetinformation">IWDFIoTarget2::FormatRequestForSetInformation</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiotarget2-formatrequestforsetinformation">FormatRequestForSetInformation</a> method formats an I/O request to set information about a file, but it does not send the request to an I/O target.

</td>
</tr>
</table> 

