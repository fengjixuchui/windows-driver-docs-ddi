---
UID: NF:ksproxy.IKsAggregateControl.KsRemoveAggregate
title: IKsAggregateControl::KsRemoveAggregate (ksproxy.h)
description: The KsRemoveAggregate method removes a previously added COM server aggregate provider from the list of interface providers for the KS object that exposes the IKsAggregateControl interface.
old-location: stream\iksaggregatecontrol_ksremoveaggregate.htm
tech.root: stream
ms.assetid: f625b1ed-ccab-4072-9eb9-c4ebbddb1199
ms.date: 04/23/2018
ms.keywords: IKsAggregateControl interface [Streaming Media Devices],KsRemoveAggregate method, IKsAggregateControl.KsRemoveAggregate, IKsAggregateControl::KsRemoveAggregate, KsRemoveAggregate, KsRemoveAggregate method [Streaming Media Devices], KsRemoveAggregate method [Streaming Media Devices],IKsAggregateControl interface, ksproxy/IKsAggregateControl::KsRemoveAggregate, ksproxy_8498ef2d-5e1e-4f04-b311-2552bd713032.xml, stream.iksaggregatecontrol_ksremoveaggregate
ms.topic: method
f1_keywords:
 - "ksproxy/IKsAggregateControl.KsRemoveAggregate"
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
- IKsAggregateControl.KsRemoveAggregate
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsAggregateControl::KsRemoveAggregate


## -description


The <b>KsRemoveAggregate</b> method removes a previously added COM server aggregate provider from the list of interface providers for the KS object that exposes the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nn-ksproxy-iksaggregatecontrol">IKsAggregateControl</a> interface.


## -parameters




### -param AggregateClass [in]

Identifies the COM server to remove.


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nn-ksproxy-iksaggregatecontrol">IKsAggregateControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nf-ksproxy-iksaggregatecontrol-ksaddaggregate">IKsAggregateControl::KsAddAggregate</a>
 

 

