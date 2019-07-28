---
UID: NN:wudfddi.IFileCallbackClose
title: IFileCallbackClose (wudfddi.h)
description: The framework can notify a driver when the driver should perform a close operation. The driver can handle the notification by registering the IFileCallbackClose interface.
old-location: wdf\ifilecallbackclose.htm
tech.root: wdf
ms.assetid: 22ecfb7b-daba-4321-bca5-4460ead8e3cd
ms.date: 02/26/2018
ms.keywords: IFileCallbackClose, IFileCallbackClose interface, IFileCallbackClose interface,described, UMDFFileObjectRef_52a9bb2c-0bf7-49db-80f0-7df5f4f131f6.xml, umdf.ifilecallbackclose, wdf.ifilecallbackclose, wudfddi/IFileCallbackClose
ms.topic: interface
f1_keywords:
 - "wudfddi/IFileCallbackClose"
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
- wudfddi.h
api_name:
- IFileCallbackClose
product:
- Windows
targetos: Windows
req.typenames: 
---

# IFileCallbackClose interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The framework can notify a driver when the driver should perform a close operation.  The driver can handle the notification by registering the <b>IFileCallbackClose</b> interface.

A driver registers the <b>IFileCallbackClose</b> interface when it calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a> method to create a device object. 


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IFileCallbackClose</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IFileCallbackClose</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IFileCallbackClose</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ifilecallbackclose-onclosefile">IFileCallbackClose::OnCloseFile</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ifilecallbackclose-onclosefile">OnCloseFile</a> method is called when the last reference count on a file object goes down to zero and before the file object is released. 

</td>
</tr>
</table> 

