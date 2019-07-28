---
UID: NC:ndkpi.NDK_FN_CONTROL_CONNECT_EVENTS
title: NDK_FN_CONTROL_CONNECT_EVENTS (ndkpi.h)
description: The NdkControlConnectEvents (NDK_FN_CONTROL_CONNECT_EVENTS) function pauses and restarts NDK connect event callback functions.
old-location: netvista\ndk_fn_control_connect_events.htm
tech.root: netvista
ms.assetid: 3AA50940-A782-4A46-8E45-077BC76D41A7
ms.date: 05/02/2018
ms.keywords: NDK_FN_CONTROL_CONNECT_EVENTS, NDK_FN_CONTROL_CONNECT_EVENTS callback, NdkControlConnectEvents, NdkControlConnectEvents callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkControlConnectEvents, netvista.ndk_fn_control_connect_events
ms.topic: callback
f1_keywords:
 - "ndkpi/NdkControlConnectEvents"
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ndkpi.h
api_name:
- NdkControlConnectEvents
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDK_FN_CONTROL_CONNECT_EVENTS callback function


## -description


The <i>NdkControlConnectEvents</i> (<i>NDK_FN_CONTROL_CONNECT_EVENTS</i>) function pauses and restarts NDK connect event callback functions.


## -parameters




### -param *pNdkListener [in]

A pointer to an NDK listener object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_listener">NDK_LISTENER</a>).


### -param Pause [in]

A BOOLEAN value that specifies if a connection is paused or restarted. If <i>Pause</i> is TRUE the connection is paused. If <i>Pause</i> is FALSE the connection is restarted.


## -returns



None




## -remarks



This function is closely related to the <i>NdkConnectEventCallback</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_connect_event_callback">NDK_FN_CONNECT_EVENT_CALLBACK</a>) function. The  <i>NDK_FN_CONNECT_EVENT_CALLBACK</i> function is called by an NDK provider to notify a consumer about an incoming connection request.
To pause the reception of connect event callbacks, an  NDK consumer can pass TRUE in the <i>Pause</i> parameter.  When a connection is  paused, the incoming connection requests must be treated as if there is no NDK listener  (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_listener">NDK_LISTENER</a>) on the targeted address.

To restart  the reception of connect event callbacks, the consumer passes FALSE in the <i>Pause</i> parameter.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_connect_event_callback">NDK_FN_CONNECT_EVENT_CALLBACK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_listener">NDK_LISTENER</a>
 

 

