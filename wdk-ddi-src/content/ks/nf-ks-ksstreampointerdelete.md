---
UID: NF:ks.KsStreamPointerDelete
title: KsStreamPointerDelete function (ks.h)
description: The KsStreamPointerDelete function deletes a clone stream pointer, releasing a reference on the frame to which this stream pointer referred.
old-location: stream\ksstreampointerdelete.htm
tech.root: stream
ms.assetid: 68819fe9-fd90-4391-a129-5aa0cae1558b
ms.date: 04/23/2018
ms.keywords: KsStreamPointerDelete, KsStreamPointerDelete function [Streaming Media Devices], avfunc_b21da27c-abf4-4277-8a22-232c31fbfe97.xml, ks/KsStreamPointerDelete, stream.ksstreampointerdelete
ms.topic: function
f1_keywords:
 - "ks/KsStreamPointerDelete"
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsStreamPointerDelete
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsStreamPointerDelete function


## -description


The<b> KsStreamPointerDelete </b>function deletes a clone stream pointer, releasing a reference on the frame to which this stream pointer referred.


## -parameters




### -param StreamPointer [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a> structure representing the clone stream pointer to delete. Must be a clone stream pointer; cannot be the leading or trailing edge stream pointer.


## -returns



None




## -remarks



If the frame to which <i>StreamPointer</i> points has no other references on it after deletion, it is completed. When the last frame in a given IRP is completed, the IRP is completed.

The leading edge and trailing edge stream pointers for a given queue and pin are special stream pointers that cannot be deleted.

Also see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/stream-pointers">Stream Pointers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kspingetleadingedgestreampointer">KsPinGetLeadingEdgeStreamPointer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kspingettrailingedgestreampointer">KsPinGetTrailingEdgeStreamPointer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ks-ksstreampointerclone">KsStreamPointerClone</a>
 

 

