---
UID: NF:storport.StorPortReleaseSpinLock
title: StorPortReleaseSpinLock function (storport.h)
description: The StorPortReleaseSpinLock routine releases a spinlock acquired by StorPortAcquireSpinLock.
old-location: storage\storportreleasespinlock.htm
tech.root: storage
ms.assetid: ed91d41a-575d-4b26-a7e0-f3ce43db76b4
ms.date: 03/29/2018
keywords: ["StorPortReleaseSpinLock function"]
ms.keywords: StorPortReleaseSpinLock, StorPortReleaseSpinLock routine [Storage Devices], storage.storportreleasespinlock, storport/StorPortReleaseSpinLock, storprt_5f3bd7a7-ffdd-4d7b-992b-70c2cea3acec.xml
f1_keywords:
 - "storport/StorPortReleaseSpinLock"
 - "StorPortReleaseSpinLock"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StorPortSpinLock, StorPortSpinLock4
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
- HeaderDef
api_location:
- storport.h
api_name:
- StorPortReleaseSpinLock
targetos: Windows
req.typenames: 
---

# StorPortReleaseSpinLock function


## -description


The <b>StorPortReleaseSpinLock</b> routine releases a spinlock acquired by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportacquirespinlock">StorPortAcquireSpinLock</a>.


## -parameters




### -param DeviceExtension

<p>Pointer to a per-adapter device extension.</p>


### -param LockHandle [in, out]

Pointer to a lock handle returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportacquirespinlock">StorPortAcquireSpinLock</a>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportacquirespinlock">StorPortAcquireSpinLock</a>
 

 

