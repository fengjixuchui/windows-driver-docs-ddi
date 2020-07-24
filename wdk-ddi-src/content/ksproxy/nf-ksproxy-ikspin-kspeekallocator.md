---
UID: NF:ksproxy.IKsPin.KsPeekAllocator
title: IKsPin::KsPeekAllocator (ksproxy.h)
description: The KsPeekAllocator method returns a pointer to an IMemAllocator interface for a pin's assigned allocator.
old-location: stream\ikspin_kspeekallocator.htm
tech.root: stream
ms.assetid: fd833d0b-2f81-4002-8280-38e17e528af6
ms.date: 04/23/2018
keywords: ["IKsPin::KsPeekAllocator"]
ms.keywords: IKsPin interface [Streaming Media Devices],KsPeekAllocator method, IKsPin.KsPeekAllocator, IKsPin::KsPeekAllocator, KsPeekAllocator, KsPeekAllocator method [Streaming Media Devices], KsPeekAllocator method [Streaming Media Devices],IKsPin interface, ksproxy/IKsPin::KsPeekAllocator, ksproxy_46ab9e52-a477-4fca-bddc-af1848484f84.xml, stream.ikspin_kspeekallocator
f1_keywords:
 - "ksproxy/IKsPin.KsPeekAllocator"
 - "IKsPin.KsPeekAllocator"
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Desktop
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
- IKsPin.KsPeekAllocator
targetos: Windows
req.typenames: 
---

# IKsPin::KsPeekAllocator


## -description


The <b>KsPeekAllocator</b> method returns a pointer to an <b>IMemAllocator</b> interface for a pin's assigned allocator.


## -parameters




### -param Operation [in]

A value that specifies the type of operation. This value can be one of the following values from the KSPEEKOPERATION enumerated type.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
<b>KsPeekOperation_PeekOnly</b>

</td>
<td>
<b>IKsPin::KsPeekAllocator </b>does not increment the reference count for the allocator. 

</td>
</tr>
<tr>
<td>
<b>KsPeekOperation_AddRef</b>

</td>
<td>
<b>IKsPin::KsPeekAllocator</b> increments the reference count for the allocator (calls AddRef). 

</td>
</tr>
</table>
 


## -returns



Returns a pointer to an <b>IMemAllocator</b> interface if successful; otherwise, returns <b>NULL</b>. 




## -remarks



For more information about <b>IMemAllocator</b>, see the Microsoft Windows SDK documentation.

This method is for proxy use and is not recommended for application use.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-ikspin">IKsPin</a>
 

 

