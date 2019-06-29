---
UID: NN:ksproxy.IKsPinEx
title: IKsPinEx (ksproxy.h)
description: The IKsPinEx interface inherits all the methods of the IKsPin interface and extends IKsPin to provide a method that notifies the filter graph of an error to give the filter graph an opportunity to halt.
old-location: stream\ikspinex.htm
tech.root: stream
ms.assetid: 9e6fd96d-c78e-44f3-ae4c-3688da48a494
ms.date: 04/23/2018
ms.keywords: IKsPinEx, IKsPinEx interface [Streaming Media Devices], IKsPinEx interface [Streaming Media Devices],described, ksproxy/IKsPinEx, ksproxy_3c92d570-f22f-4165-bafd-9a22f5516137.xml, stream.ikspinex
ms.topic: interface
req.header: ksproxy.h
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
- IKsPinEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsPinEx interface


## -description


The <b>IKsPinEx</b> interface inherits all the methods of the <b>IKsPin</b> interface and extends <b>IKsPin</b> to provide a method that notifies the filter graph of an error to give the filter graph an opportunity to halt.

The IID for this interface is IID_IKsPinEx.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsPinEx</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nn-ksproxy-ikspin">IKsPin</a>. <b>IKsPinEx</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IKsPinEx</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nf-ksproxy-ikspinex-ksnotifyerror">KsNotifyError</a>
</td>
<td align="left" width="63%">
Notifies the filter graph of an error to give the filter graph an opportunity to halt.

</td>
</tr>
</table> 


## -remarks



An interface handler (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nn-ksproxy-iksinterfacehandler">IKsInterfaceHandler</a>) uses many of the <b>IKsPinEx</b> methods to route media samples of a particular media type. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nn-ksproxy-iksinterfacehandler">IKsInterfaceHandler</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nn-ksproxy-ikspin">IKsPin</a>
 

 

