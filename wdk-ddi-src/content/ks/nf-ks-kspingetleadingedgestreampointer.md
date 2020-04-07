---
UID: NF:ks.KsPinGetLeadingEdgeStreamPointer
title: KsPinGetLeadingEdgeStreamPointer function (ks.h)
description: The KsPinGetLeadingEdgeStreamPointer function acquires the leading edge stream pointer for the queue associated with the given pin.
old-location: stream\kspingetleadingedgestreampointer.htm
tech.root: stream
ms.assetid: 05615730-dbeb-496a-b4a8-a16830b31586
ms.date: 04/23/2018
keywords: ["KsPinGetLeadingEdgeStreamPointer function"]
ms.keywords: KsPinGetLeadingEdgeStreamPointer, KsPinGetLeadingEdgeStreamPointer function [Streaming Media Devices], avfunc_0eb1faec-c090-4647-8306-84cff42ddf9c.xml, ks/KsPinGetLeadingEdgeStreamPointer, stream.kspingetleadingedgestreampointer
f1_keywords:
 - "ks/KsPinGetLeadingEdgeStreamPointer"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsPinGetLeadingEdgeStreamPointer
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinGetLeadingEdgeStreamPointer function


## -description


The<b> KsPinGetLeadingEdgeStreamPointer</b> function acquires the leading edge stream pointer for the queue associated with the given pin.


## -parameters




### -param Pin [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure owning the queue for which the leading edge stream pointer should be acquired.


### -param State [in]

This parameter specifies how to acquire the leading edge stream pointer. Can be one of the following:





#### KSSTREAM_POINTER_STATE_UNLOCKED

Acquire the leading edge stream pointer regardless of whether it references a data frame or not. 

No attempts can be made to access any data associated with the pointer until the pointer is locked. Also note that frames associated with an unlocked stream pointer can be canceled.



#### KSSTREAM_POINTER_STATE_LOCKED

Acquire and lock the leading edge stream pointer. If no data frame is associated with the stream pointer, return <b>NULL</b>. If a non<b>null</b> pointer is returned, it is a locked stream pointer and has a data frame associated with it. Frames associated with a locked stream pointer <b>cannot</b> be canceled. 


## -returns



<b>KsPinGetLeadingEdgeStreamPointer</b> returns a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a> structure or <b>NULL</b>. A return value of <b>NULL</b> may occur because there is no queue associated with the pin, indicating that the pin does not use the standard transport mechanism. Alternatively, a return value of <b>NULL</b> may occur because an attempt to lock the leading edge failed, indicating that there is no data frame associated with the leading edge.




## -remarks



Filters that implement <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/pin-centric-processing">Pin-Centric Processing</a> often call <b>KsPinGetLeadingEdgeStreamPointer</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingettrailingedgestreampointer">KsPinGetTrailingEdgeStreamPointer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksstreampointeradvance">KsStreamPointerAdvance</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksstreampointeradvanceoffsetsandunlock">KsStreamPointerAdvanceOffsetsAndUnlock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ks-ksstreampointerclone">KsStreamPointerClone</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksstreampointerdelete">KsStreamPointerDelete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ks-ksstreampointerlock">KsStreamPointerLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksstreampointerunlock">KsStreamPointerUnlock</a>
 

 

