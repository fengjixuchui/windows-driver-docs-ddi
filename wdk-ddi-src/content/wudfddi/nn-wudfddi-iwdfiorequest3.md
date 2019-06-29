---
UID: NN:wudfddi.IWDFIoRequest3
title: IWDFIoRequest3 (wudfddi.h)
description: To obtain the IWDFIoRequest3 interface, drivers call IWDFIoRequest::QueryInterface.
old-location: wdf\iwdfiorequest3.htm
tech.root: wdf
ms.assetid: 12F4CDB7-EEA5-49D1-AD41-6F5F0C9ED6C3
ms.date: 02/26/2018
ms.keywords: IWDFIoRequest3, IWDFIoRequest3 interface, IWDFIoRequest3 interface,described, umdf.iwdfiorequest3, wdf.iwdfiorequest3, wudfddi/IWDFIoRequest3
ms.topic: interface
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
- IWDFIoRequest3
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest3 interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

To obtain the <b>IWDFIoRequest3</b> interface, drivers call <b>IWDFIoRequest::QueryInterface</b>.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFIoRequest3</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfiorequest2">IWDFIoRequest2</a>. <b>IWDFIoRequest3</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFIoRequest3</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest3-getusermodedriverinitiatedio">GetUserModeDriverInitiatedIo</a>
</td>
<td align="left" width="63%">

   The 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest3-getusermodedriverinitiatedio">GetUserModeDriverInitiatedIo</a> method determines whether an I/O request is marked as initiated by a UMDF driver.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest3-retrieveactivityid">RetrieveActivityId</a>
</td>
<td align="left" width="63%">

   The 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest3-retrieveactivityid">RetrieveActivityId</a> method retrieves the current activity identifier associated with an I/O request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest3-setactivityid">SetActivityId</a>
</td>
<td align="left" width="63%">

   The 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest3-setactivityid">SetActivityId</a> method associates an activity identifier with an I/O request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest3-setusermodedriverinitiatedio">SetUserModeDriverInitiatedIo</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest3-setusermodedriverinitiatedio">SetUserModeDriverInitiatedIo</a> method 
   
  indicates to kernel-mode drivers that sit below the UMDF driver in the same device stack that a particular request should be treated as though it came from a UMDF driver.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfiorequest2">IWDFIoRequest2</a>
 

 

