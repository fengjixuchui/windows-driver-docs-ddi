---
UID: NN:wudfddi.IWDFIoTarget
title: IWDFIoTarget (wudfddi.h)
description: The IWDFIoTarget interface exposes the I/O target object that typically represents a lower driver in the stack.
old-location: wdf\iwdfiotarget.htm
tech.root: wdf
ms.assetid: bebe79c8-28d1-4976-b314-b73e6e9b7b9c
ms.date: 02/26/2018
ms.keywords: IWDFIoTarget, IWDFIoTarget interface, IWDFIoTarget interface,described, UMDFIoTargetObjectRef_3def2530-811a-4ac8-b9bd-c39cc4cb8fb2.xml, umdf.iwdfiotarget, wdf.iwdfiotarget, wudfddi/IWDFIoTarget
ms.topic: interface
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
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
- IWDFIoTarget
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoTarget interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFIoTarget</b> interface exposes the I/O target object that typically represents a lower driver in the stack.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFIoTarget</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfobject">IWDFObject</a>. <b>IWDFIoTarget</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFIoTarget</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiotarget-cancelsentrequestsforfile">IWDFIoTarget::CancelSentRequestsForFile</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiotarget-cancelsentrequestsforfile">CancelSentRequestsForFile</a> method cancels all I/O requests that have been sent on behalf of the specified file object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiotarget-formatrequestforioctl">IWDFIoTarget::FormatRequestForIoctl</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiotarget-formatrequestforioctl">FormatRequestForIoctl</a> method formats an I/O request object for an I/O control operation.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiotarget-formatrequestforread">IWDFIoTarget::FormatRequestForRead</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiotarget-formatrequestforread">FormatRequestForRead</a> method formats an I/O request object for a read operation.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiotarget-formatrequestforwrite">IWDFIoTarget::FormatRequestForWrite</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiotarget-formatrequestforwrite">FormatRequestForWrite</a> method formats an I/O request object for a write operation.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiotarget-gettargetfile">IWDFIoTarget::GetTargetFile</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiotarget-gettargetfile">GetTargetFile</a> method retrieves the framework file object that is associated with the I/O target object.

</td>
</tr>
</table> 

