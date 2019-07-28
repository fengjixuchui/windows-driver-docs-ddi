---
UID: NF:ks.KsFilterFactoryGetNextSiblingFilterFactory
title: KsFilterFactoryGetNextSiblingFilterFactory function (ks.h)
description: The KsFilterFactoryGetNextSiblingFilterFactory function returns the next filter factory belonging to the parent device of FilterFactory.
old-location: stream\ksfilterfactorygetnextsiblingfilterfactory.htm
tech.root: stream
ms.assetid: e397d36c-3f28-4a70-9b4a-f13be094d47b
ms.date: 04/23/2018
ms.keywords: KsFilterFactoryGetNextSiblingFilterFactory, KsFilterFactoryGetNextSiblingFilterFactory function [Streaming Media Devices], avfunc_b1bdc37b-de4a-4cfb-b1e9-1201225c29ab.xml, ks/KsFilterFactoryGetNextSiblingFilterFactory, stream.ksfilterfactorygetnextsiblingfilterfactory
ms.topic: function
f1_keywords:
 - "ks/KsFilterFactoryGetNextSiblingFilterFactory"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KsFilterFactoryGetNextSiblingFilterFactory
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsFilterFactoryGetNextSiblingFilterFactory function


## -description


The<b> KsFilterFactoryGetNextSiblingFilterFactory</b> function returns the next filter factory belonging to the parent device of <i>FilterFactory</i>.


## -parameters




### -param FilterFactory [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a> for which to return the next filter factory of its parent device.


## -returns



<b>KsFilterFactoryGetNextSiblingFilterFactory</b> returns a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a> structure that represents the next sibling filter factory of <i>FilterFactory</i>. If no such filter factory exists, <b>NULL</b> is returned.




## -remarks



This call is an inline function call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksgetnextsibling">KsGetNextSibling</a>. Note that the object hierarchy is guaranteed to be stable only while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksdevicegetfirstchildfilterfactory">KsDeviceGetFirstChildFilterFactory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksgetnextsibling">KsGetNextSibling</a>
 

 

