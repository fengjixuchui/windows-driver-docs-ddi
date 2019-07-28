---
UID: NF:fcb.RxpReferenceNetFcb
title: RxpReferenceNetFcb function (fcb.h)
description: RxpReferenceNetFcb increments the reference count on an FCB.
old-location: ifsk\rxpreferencenetfcb.htm
tech.root: ifsk
ms.assetid: bc8999e2-d305-407f-8302-6834efa698c5
ms.date: 04/16/2018
ms.keywords: RxpReferenceNetFcb, RxpReferenceNetFcb function [Installable File System Drivers], fcb/RxpReferenceNetFcb, ifsk.rxpreferencenetfcb, rxref_48d7801e-1459-405e-a681-2aa13e9e31cd.xml
ms.topic: function
f1_keywords:
 - "fcb/RxpReferenceNetFcb"
req.header: fcb.h
req.include-header: Fcb.h
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
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- fcb.h
api_name:
- RxpReferenceNetFcb
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxpReferenceNetFcb function


## -description


<b>RxpReferenceNetFcb</b> increments the reference count on an FCB.


## -parameters




### -param Fcb

A pointer to the FCB structure to be referenced.


## -returns



<b>RxpReferenceNetFcb</b> returns the final reference count after the reference. 




## -remarks



A number of debugging macros are defined in <i>fcb.h</i> that are the preferred way to call this routine. These macros provide a wrapper around the <b>RxpReferenceNetFcb</b> or <b>RxpDereferenceNetFcb</b> routines used for file structure management operations on FCB structures. The <b>RxReferenceNetFcb</b> macro is the preferred way to call this routine. This macro first calls the <b>RxpTrackReference</b> routine to log diagnostic information about the request before calling the <b>RxpReferenceNetFcb</b> routine.

On checked builds, <b>RxpReferenceNetFcb</b> causes the system to ASSERT if the node type for the structure is not an FCB. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fcb/nf-fcb-rxpdereferencenetfcb">RxpDereferenceNetFcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fcb/nf-fcb-rxptrackdereference">RxpTrackDereference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fcb/nf-fcb-rxptrackreference">RxpTrackReference</a>
 

 

