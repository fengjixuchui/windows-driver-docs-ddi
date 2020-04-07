---
UID: NN:wudfddi.IPowerPolicyCallbackWakeFromSx
title: IPowerPolicyCallbackWakeFromSx (wudfddi.h)
description: A driver's IPowerPolicyCallbackWakeFromSx interface provides callback functions that the framework calls to notify the driver about wake events. These events are related to a device's ability to wake both itself and the system from a low-power state.
old-location: wdf\ipowerpolicycallbackwakefromsx.htm
tech.root: wdf
ms.assetid: dac93565-e67a-44a3-acf0-e1f58ce8dd9e
ms.date: 02/26/2018
keywords: ["IPowerPolicyCallbackWakeFromSx interface"]
ms.keywords: IPowerPolicyCallbackWakeFromSx, IPowerPolicyCallbackWakeFromSx interface, IPowerPolicyCallbackWakeFromSx interface,described, UMDFDeviceObjectRef_bc620403-691d-42df-9bdf-2a859e5718ea.xml, umdf.ipowerpolicycallbackwakefromsx, wdf.ipowerpolicycallbackwakefromsx, wudfddi/IPowerPolicyCallbackWakeFromSx
f1_keywords:
 - "wudfddi/IPowerPolicyCallbackWakeFromSx"
req.header: wudfddi.h
req.include-header: Wudfddi.h
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
- IPowerPolicyCallbackWakeFromSx
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPowerPolicyCallbackWakeFromSx interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>IPowerPolicyCallbackWakeFromSx</b> interface provides callback functions that the framework calls to notify the driver about wake events. These events are related to a device's ability to wake both itself and the system from a low-power state.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPowerPolicyCallbackWakeFromSx</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPowerPolicyCallbackWakeFromSx</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -remarks



If your driver supports an <b>IPowerPolicyCallbackWakeFromSx</b> interface for a device, the <b>IUnknown::QueryInterface</b> method that the driver passes to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a> must return the interface. 



