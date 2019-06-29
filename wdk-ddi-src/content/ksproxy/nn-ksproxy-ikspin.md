---
UID: NN:ksproxy.IKsPin
title: IKsPin (ksproxy.h)
description: The IKsPin interface provides methods that control and retrieve information about a pin.
old-location: stream\ikspin.htm
tech.root: stream
ms.assetid: 4717300c-bc98-4e1f-83c3-cbd368b45140
ms.date: 04/23/2018
ms.keywords: IKsPin, IKsPin interface [Streaming Media Devices], IKsPin interface [Streaming Media Devices],described, ksproxy/IKsPin, ksproxy_9a020f8a-1271-47ea-816f-1132e44b6f45.xml, stream.ikspin
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- ksproxy.h
api_name:
- IKsPin
- IKsPin.KsReceiveAllocator
- IKsPin.KsRenegotiateAllocator
- IKsPin.KsQualityNotify
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsPin interface


## -description


The <b>IKsPin</b> interface provides methods that control and retrieve information about a pin.

The IID for this interface is IID_IKsPin.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsPin</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IKsPin</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IKsPin</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nf-ksproxy-ikspin-kscreatesinkpinhandle">KsCreateSinkPinHandle</a>
</td>
<td align="left" width="63%">
For proxy use and not recommended for application use. Creates a pin handle and stores it in the KS pin object. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nf-ksproxy-ikspin-ksdecrementpendingiocount">KsDecrementPendingIoCount</a>
</td>
<td align="left" width="63%">
Decrements the number of I/O operations that are in progress on a pin.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nf-ksproxy-ikspin-ksdeliver">KsDeliver</a>
</td>
<td align="left" width="63%">
Delivers a media sample from an output pin to an input pin. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nf-ksproxy-ikspin-ksgetcurrentcommunication">KsGetCurrentCommunication</a>
</td>
<td align="left" width="63%">
Retrieves the current communication direction, interface, and medium of a pin. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nf-ksproxy-ikspin-ksincrementpendingiocount">KsIncrementPendingIoCount</a>
</td>
<td align="left" width="63%">
Increments the number of I/O operations that are in progress on a pin.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nf-ksproxy-ikspin-ksmediasamplescompleted">KsMediaSamplesCompleted</a>
</td>
<td align="left" width="63%">
Informs a pin that a stream segment completed. Used by interface handlers.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nf-ksproxy-ikspin-kspeekallocator">KsPeekAllocator</a>
</td>
<td align="left" width="63%">
For proxy use and not recommended for application use. Returns a pointer to a <b>IMemAllocator</b> interface for a pin's assigned allocator.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nf-ksproxy-ikspin-kspropagateacquire">KsPropagateAcquire</a>
</td>
<td align="left" width="63%">
For proxy use and not recommended for application use.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>KsQualityNotify</b></td>
<td align="left" width="63%">
For proxy use and not recommended for application use. Receives quality-management reports from the kernel-mode equivalent of a DirectShow pin.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nf-ksproxy-ikspin-ksqueryinterfaces">KsQueryInterfaces</a>
</td>
<td align="left" width="63%">
Retrieves interfaces that a pin supports.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nf-ksproxy-ikspin-ksquerymediums">KsQueryMediums</a>
</td>
<td align="left" width="63%">
Retrieves mediums that a pin supports.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>KsReceiveAllocator</b></td>
<td align="left" width="63%">
For proxy use and not recommended for application use. Provides an allocator for an output pin. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>KsRenegotiateAllocator</b></td>
<td align="left" width="63%">
Obsolete. Do not use.

</td>
</tr>
</table> 


## -remarks



An interface handler (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nn-ksproxy-iksinterfacehandler">IKsInterfaceHandler</a>) uses many of the <b>IKsPin</b> methods to route media samples of a particular media type. 
    




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nn-ksproxy-iksinterfacehandler">IKsInterfaceHandler</a>
 

 

