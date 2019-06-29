---
UID: NN:wudfddi.IPowerPolicyCallbackWakeFromS0
title: IPowerPolicyCallbackWakeFromS0 (wudfddi.h)
description: A driver's IPowerPolicyCallbackWakeFromS0 interface provides callback functions that the framework calls to notify the driver about wake events.
old-location: wdf\ipowerpolicycallbackwakefroms0.htm
tech.root: wdf
ms.assetid: d1b29916-9800-4276-860c-f7d143deb962
ms.date: 02/26/2018
ms.keywords: IPowerPolicyCallbackWakeFromS0, IPowerPolicyCallbackWakeFromS0 interface, IPowerPolicyCallbackWakeFromS0 interface,described, UMDFDeviceObjectRef_e79ecf1d-279d-4945-941a-ed53b00f6242.xml, umdf.ipowerpolicycallbackwakefroms0, wdf.ipowerpolicycallbackwakefroms0, wudfddi/IPowerPolicyCallbackWakeFromS0
ms.topic: interface
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
- IPowerPolicyCallbackWakeFromS0
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPowerPolicyCallbackWakeFromS0 interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>IPowerPolicyCallbackWakeFromS0</b> interface provides callback functions that the framework calls to notify the driver about wake events. These events are related to a device's ability to wake from a low-power state while the system remains in the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-working-state-s0">system working state</a> (S0).


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPowerPolicyCallbackWakeFromS0</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPowerPolicyCallbackWakeFromS0</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPowerPolicyCallbackWakeFromS0</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipowerpolicycallbackwakefroms0-onarmwakefroms0">IPowerPolicyCallbackWakeFromS0::OnArmWakeFromS0</a>
</td>
<td align="left" width="63%">
A driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipowerpolicycallbackwakefroms0-onarmwakefroms0">OnArmWakeFromS0</a> callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state, if the system remains in the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-working-state-s0">system working state</a> (S0). 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipowerpolicycallbackwakefroms0-ondisarmwakefroms0">IPowerPolicyCallbackWakeFromS0::OnDisarmWakeFromS0</a>
</td>
<td align="left" width="63%">
A driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipowerpolicycallbackwakefroms0-ondisarmwakefroms0">OnDisarmWakeFromS0</a> event callback function disarms (that is, disables) a device's ability to trigger a wake signal while in a low-power device state, if the system remains in the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-working-state-s0">system working state</a> (S0). 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipowerpolicycallbackwakefroms0-onwakefroms0triggered">IPowerPolicyCallbackWakeFromS0::OnWakeFromS0Triggered</a>
</td>
<td align="left" width="63%">
A driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipowerpolicycallbackwakefroms0-onwakefroms0triggered">OnWakeFromS0Triggered</a> event callback function informs the driver that its device, which had previously entered a low-power device state while the system power state remained at S0, might have triggered a wake signal.

</td>
</tr>
</table> 


## -remarks



If your driver supports an <b>IPowerPolicyCallbackWakeFromS0</b> interface for a device, the <b>IUnknown::QueryInterface</b> method that the driver passes to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a> must return the interface. 



