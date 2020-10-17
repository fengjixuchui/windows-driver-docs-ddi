---
UID: NN:wudfddi.IWDFCmResourceList
title: IWDFCmResourceList (wudfddi.h)
description: This interface represents a list of hardware resources for a device.
old-location: wdf\iwdfcmresourcelist.htm
tech.root: wdf
ms.assetid: 8C03A1A3-1757-4622-9652-0D84DC0AFE59
ms.date: 02/26/2018
keywords: ["IWDFCmResourceList interface"]
ms.keywords: IWDFCmResourceList, IWDFCmResourceList interface, IWDFCmResourceList interface,described, umdf.iwdfcmresourcelist, wdf.iwdfcmresourcelist, wudfddi/IWDFCmResourceList
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFCmResourceList
 - wudfddi/IWDFCmResourceList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFCmResourceList
---

# IWDFCmResourceList interface


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

This interface represents a list of hardware resources for a device.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFCmResourceList</b> interface inherits from <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfobject">IWDFObject</a>. <b>IWDFCmResourceList</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -remarks

After a UMDF driver receives a translated resource list in its <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackhardware2-onpreparehardware">OnPrepareHardware</a> callback, it can use <b>IWDFCmResourceList</b> to scan through the list and identify its port and register resources.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfresource/">Framework Resource-List Object Methods</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfobject">IWDFObject</a>