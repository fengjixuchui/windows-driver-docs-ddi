---
UID: NC:netrequestqueue.EVT_NET_REQUEST_QUERY_DATA
title: EVT_NET_REQUEST_QUERY_DATA (netrequestqueue.h)
description: Implemented by the client driver to handle a specific OID query request.
tech.root: netvista
ms.assetid: 1ae913de-77da-4622-9a79-72a34e4705ab
ms.date: 02/08/2018
keywords: ["EVT_NET_REQUEST_QUERY_DATA callback function"]
f1_keywords:
 - "netrequestqueue/NetRequestWdmGetNdisOidRequest"
 - "NetRequestWdmGetNdisOidRequest"
req.header: netrequestqueue.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
req.alt-api:
req.alt-loc:
topictype: 
- apiref
apitype: 
- UserDefined
apilocation: 
- netrequestqueue.h
apiname: 
- EVT_NET_REQUEST_QUERY_DATA
targetos: Windows
---

# EVT_NET_REQUEST_QUERY_DATA callback function

## -description



Implemented by the client driver to handle a specific OID query request.

## -prototype

```c++
//Declaration

EVT_NET_REQUEST_QUERY_DATA EvtNetRequestQueryData; 

// Definition

VOID EvtNetRequestQueryData 
(
	_In_	NETREQUESTQUEUE	RequestQueue,
	_In_	NETREQUEST 		Request,
	_Out_	void * 			OutputBuffer,
	_In_	UINT 			OutputBufferLength
)
{...}

typedef EVT_NET_REQUEST_QUERY_DATA *PFN_NET_REQUEST_QUERY_DATA;
```

## -parameters

### -param RequestQueue 
A handle to a net request queue object.

### -param Request 
A handle to a network request object.

### -param OutputBuffer 
A pointer to a caller-supplied buffer.

### -param OutputBufferLength 
The length, in bytes, of the request's output buffer, if an output buffer is available.

## -remarks
To register an *EVT_NET_REQUEST_QUERY_DATA* callback function, the client driver calls [NET_REQUEST_QUEUE_CONFIG_ADD_QUERY_DATA_HANDLER](nf-netrequestqueue-net_request_queue_config_add_query_data_handler.md) or [NET_REQUEST_QUEUE_CONFIG_ADD_INITIALIZED_QUERY_DATA_HANDLER](nf-netrequestqueue-net_request_queue_config_add_initialized_query_data_handler.md), and then calls [NetRequestQueueCreate](nf-netrequestqueue-netrequestqueuecreate.md).

Your client driver can provide one or more specialized handlers for specific OID query requests. In addition, it can also provide a generic *[EVT_NET_REQUEST_DEFAULT_QUERY_DATA](nc-netrequestqueue-evt_net_request_default_query_data.md)* callback function.



## -see-also
