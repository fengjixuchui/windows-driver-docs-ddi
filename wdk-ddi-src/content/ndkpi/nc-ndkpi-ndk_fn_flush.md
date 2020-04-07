---
UID: NC:ndkpi.NDK_FN_FLUSH
title: NDK_FN_FLUSH (ndkpi.h)
description: The NdkFlush (NDK_FN_FLUSH) function initiates cancelling of the receive and the initiator queue requests that are currently pending on an NDK queue pair (QP) object.
old-location: netvista\ndk_fn_flush.htm
tech.root: netvista
ms.assetid: 8C5F62DD-36CB-4EBC-9113-BB5BF19C0D45
ms.date: 05/02/2018
keywords: ["NDK_FN_FLUSH callback function"]
ms.keywords: NDK_FN_FLUSH, NDK_FN_FLUSH callback, NdkFlush, NdkFlush callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkFlush, netvista.ndk_fn_flush
f1_keywords:
 - "ndkpi/NdkFlush"
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ndkpi.h
api_name:
- NdkFlush
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDK_FN_FLUSH callback function


## -description


The <i>NdkFlush</i> (<i>NDK_FN_FLUSH</i>) function initiates cancelling of the receive and the initiator queue requests that are currently pending on an NDK queue pair (QP) object.


## -parameters




### -param *pNdkQp [in]

A pointer to an NDK queue pair (QP) object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_qp">NDK_QP</a>).


## -remarks



<i>NdkFlush</i> cancels the receive and the initiator queue requests that are currently pending on a QP. The flushed requests have STATUS_CANCELLED as completion status.

If the  NDK consumer wants to verify that all of the requests are flushed after issuing <i>NdkFlush</i>, the consumer must empty the CQ until it sees completions for all requests that were queued prior to calling <i>NdkFlush</i>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_qp">NDK_QP</a>
 

 

