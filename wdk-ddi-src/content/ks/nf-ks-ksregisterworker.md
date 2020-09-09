---
UID: NF:ks.KsRegisterWorker
title: KsRegisterWorker function (ks.h)
description: The KsRegisterWorker function handles clients registering for use of a thread.
old-location: stream\ksregisterworker.htm
tech.root: stream
ms.assetid: b9c74a56-3f2c-4b94-8fb2-6b44075ec34b
ms.date: 04/23/2018
keywords: ["KsRegisterWorker function"]
ms.keywords: KsRegisterWorker, KsRegisterWorker function [Streaming Media Devices], ks/KsRegisterWorker, ksfunc_c2cb48b6-6268-4d53-a81b-07c1984f80aa.xml, stream.ksregisterworker
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KsRegisterWorker
 - ks/KsRegisterWorker
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsRegisterWorker
---

# KsRegisterWorker function


## -description

The **KsRegisterWorker** function handles clients registering for use of a thread. The function can create a new thread of the specified priority if there are currently no free threads available. This must be matched by a corresponding **KsUnregisterWorker** when thread use is completed. The function can only be called at PASSIVE_LEVEL.

```cpp
typedef PVOID PKSWORKER;
```

The worker routines function on opaque PKSWORKER objects that are created for each work item queued at one time.

## -parameters

### -param WorkQueueType 

[in]
Specifies the priority of the thread to create. This is usually either **CriticalWorkQueue**, **DelayedWorkQueue**, or **HyperCriticalWorkQueue**.

### -param Worker 

[out]
Location to put the opaque context that must be used when scheduling a work item. This contains the queue type and is used to synchronize completion of work items.

## -returns

The **KsRegisterWorker** function returns STATUS_SUCCESS if a worker was initialized, or if unsuccessful the function returns a thread or parameter error.

