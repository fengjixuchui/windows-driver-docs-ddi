---
UID: NF:ksproxy.IKsClockPropertySet.KsSetCorrelatedPhysicalTime
title: IKsClockPropertySet::KsSetCorrelatedPhysicalTime (ksproxy.h)
description: The KsSetCorrelatedPhysicalTime method sets the physical time with the correlated system time on the underlying clock.
old-location: stream\iksclockpropertyset_kssetcorrelatedphysicaltime.htm
tech.root: stream
ms.assetid: 208fecc5-f01f-41f3-80d3-d811b3f4173a
ms.date: 04/23/2018
keywords: ["IKsClockPropertySet::KsSetCorrelatedPhysicalTime"]
ms.keywords: IKsClockPropertySet interface [Streaming Media Devices],KsSetCorrelatedPhysicalTime method, IKsClockPropertySet.KsSetCorrelatedPhysicalTime, IKsClockPropertySet::KsSetCorrelatedPhysicalTime, KsSetCorrelatedPhysicalTime, KsSetCorrelatedPhysicalTime method [Streaming Media Devices], KsSetCorrelatedPhysicalTime method [Streaming Media Devices],IKsClockPropertySet interface, ksproxy/IKsClockPropertySet::KsSetCorrelatedPhysicalTime, ksproxy_253f05af-d07c-4f27-bfad-0006c94b8b48.xml, stream.iksclockpropertyset_kssetcorrelatedphysicaltime
f1_keywords:
 - "ksproxy/IKsClockPropertySet.KsSetCorrelatedPhysicalTime"
 - "IKsClockPropertySet.KsSetCorrelatedPhysicalTime"
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
- IKsClockPropertySet.KsSetCorrelatedPhysicalTime
targetos: Windows
req.typenames: 
---

# IKsClockPropertySet::KsSetCorrelatedPhysicalTime


## -description


The <b>KsSetCorrelatedPhysicalTime</b> method sets the physical time with the correlated system time on the underlying clock. 


## -parameters




### -param CorrelatedTime [in]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-kscorrelated_time">KSCORRELATED_TIME</a> structure that contains the physical clock time along with the correlated system time to which to set the underlying clock. 


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -remarks



The proxy uses the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-clock-correlatedphysicaltime">KSPROPERTY_CLOCK_CORRELATEDPHYSICALTIME</a> property to set the correlated time. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksclockpropertyset-ksgetcorrelatedphysicaltime">IKsClockPropertySet::KsGetCorrelatedPhysicalTime</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-kscorrelated_time">KSCORRELATED_TIME</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-clock-correlatedphysicaltime">KSPROPERTY_CLOCK_CORRELATEDPHYSICALTIME</a>
 

 

