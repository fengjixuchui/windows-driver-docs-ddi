---
UID: NN:wudfddi.IWDFRemoteInterfaceInitialize
title: IWDFRemoteInterfaceInitialize (wudfddi.h)
description: UMDF-based drivers receive the IWDFRemoteInterfaceInitialize interface as input to an IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival callback function.
old-location: wdf\iwdfremoteinterfaceinitialize.htm
tech.root: wdf
ms.assetid: 54954874-d67a-4e8b-b791-105e8018f8ca
ms.date: 02/26/2018
ms.keywords: IWDFRemoteInterfaceInitialize, IWDFRemoteInterfaceInitialize interface, IWDFRemoteInterfaceInitialize interface,described, UMDFIoTargetObjectRef_0536631b-c316-41e7-856b-94a3c991c318.xml, umdf.iwdfremoteinterfaceinitialize, wdf.iwdfremoteinterfaceinitialize, wudfddi/IWDFRemoteInterfaceInitialize
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
- IWDFRemoteInterfaceInitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFRemoteInterfaceInitialize interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

UMDF-based drivers receive the <b>IWDFRemoteInterfaceInitialize</b> interface as input to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackremoteinterfacenotification-onremoteinterfacearrival">IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival</a> callback function.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFRemoteInterfaceInitialize</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IWDFRemoteInterfaceInitialize</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFRemoteInterfaceInitialize</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfremoteinterfaceinitialize-getinterfaceguid">IWDFRemoteInterfaceInitialize::GetInterfaceGuid</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfremoteinterfaceinitialize-getinterfaceguid">GetInterfaceGuid</a> method retrieves the GUID that identifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">device interface</a>. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfremoteinterfaceinitialize-retrievesymboliclink">IWDFRemoteInterfaceInitialize::RetrieveSymbolicLink</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfremoteinterfaceinitialize-retrievesymboliclink">RetrieveSymbolicLink</a> method retrieves the symbolic link name that the operating system assigned to a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">device interface</a>. 

</td>
</tr>
</table> 

