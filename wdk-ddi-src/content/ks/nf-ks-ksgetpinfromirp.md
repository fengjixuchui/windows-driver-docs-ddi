---
UID: NF:ks.KsGetPinFromIrp
title: KsGetPinFromIrp function (ks.h)
description: The KsGetPinFromIrp function returns the AVStream pin object associated with the given IRP.
old-location: stream\ksgetpinfromirp.htm
tech.root: stream
ms.assetid: 96176a33-0721-4a4d-ba1b-131e25fc2306
ms.date: 04/23/2018
ms.keywords: KsGetPinFromIrp, KsGetPinFromIrp function [Streaming Media Devices], avfunc_fa403f21-cccb-4a57-b40a-e7531feac721.xml, ks/KsGetPinFromIrp, stream.ksgetpinfromirp
ms.topic: function
f1_keywords:
 - "ks/KsGetPinFromIrp"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsGetPinFromIrp
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsGetPinFromIrp function


## -description


The<b> KsGetPinFromIrp</b> function returns the AVStream pin object associated with the given IRP. 


## -parameters




### -param Irp [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_irp">IRP</a> for which to return the associated pin.


## -returns



<b>KsGetPinFromIrp</b> returns a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_kspin">KSPIN</a> structure associated with the given IRP or <b>NULL</b>. <b>NULL</b> indicates that either the IRP is not associated with an AVStream object or that it is associated with a filter or a topology node.




## -remarks



Currently, IRPs associated with topology nodes cannot be queried for associated pins. This may change in a future revision of AVStream.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksacquirecontrol">KsAcquireControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksfilteracquirecontrol">KsFilterAcquireControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksfilterreleasecontrol">KsFilterReleaseControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksgetfilterfromirp">KsGetFilterFromIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksgetnodeidfromirp">KsGetNodeIdFromIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksreleasecontrol">KsReleaseControl</a>
 

 

