---
UID: NN:ksproxy.IKsControl
title: IKsControl (ksproxy.h)
description: The IKsControl interface provides user-mode methods that control a KS filter or KS pin. See the IKsControl AVStream COM interface for information about the user-mode equivalent of this interface.
old-location: stream\ikscontrol.htm
tech.root: stream
ms.assetid: d73cf2fc-15bb-4f45-aae3-fb55bcd072a3
ms.date: 04/23/2018
ms.keywords: IKsControl, IKsControl interface [Streaming Media Devices], IKsControl interface [Streaming Media Devices],described, ksproxy/IKsControl, ksproxy_59a4df2f-d723-499a-adc6-907c0592a6ac.xml, stream.ikscontrol
ms.topic: interface
req.header: ksproxy.h
req.include-header: Ksproxy.h
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
req.lib: Ksproxy.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Ksproxy.lib
- Ksproxy.dll
api_name:
- IKsControl
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsControl interface


## -description


The <b>IKsControl</b> interface provides user-mode methods that control a KS filter or KS pin. See the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nn-ksproxy-ikscontrol">IKsControl</a> AVStream COM interface for information about the user-mode equivalent of this interface. 


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsControl</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IKsControl</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IKsControl</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/previous-versions/ff561744(v=vs.85)">KsEvent</a>
</td>
<td align="left" width="63%">
Enables or disables an event.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/previous-versions/ff563398(v=vs.85)">KsMethod</a>
</td>
<td align="left" width="63%">
Sends a method to a KS object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KsProperty</a>
</td>
<td align="left" width="63%">
Sets a property or retrieves property information.

</td>
</tr>
</table> 


## -remarks



The IID for this interface is IID_IKsControl.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nn-ks-ikscontrol">IKsControl (AVStream COM Interface)</a>
 

 

