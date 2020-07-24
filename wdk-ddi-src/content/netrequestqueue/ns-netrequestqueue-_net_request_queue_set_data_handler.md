---
UID: NS:netrequestqueue._NET_REQUEST_QUEUE_SET_DATA_HANDLER
title: _NET_REQUEST_QUEUE_SET_DATA_HANDLER (netrequestqueue.h)
description: Reserved for internal use. Call NET_REQUEST_QUEUE_CONFIG_ADD_SET_DATA_HANDLER to add a caller-provided handler for a specific OID set request.
tech.root: netvista
ms.assetid: c5af08b7-0733-481d-a6ba-32a21dd7990f
ms.date: 02/09/2018
keywords: ["_NET_REQUEST_QUEUE_SET_DATA_HANDLER structure"]
f1_keywords:
 - "netrequestqueue/NET_REQUEST_QUEUE_SET_DATA_HANDLER"
 - "NET_REQUEST_QUEUE_SET_DATA_HANDLER"
ms.keywords: _NET_REQUEST_QUEUE_SET_DATA_HANDLER, *PNET_REQUEST_QUEUE_SET_DATA_HANDLER, NET_REQUEST_QUEUE_SET_DATA_HANDLER, 
req.header: netrequestqueue.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_REQUEST_QUEUE_SET_DATA_HANDLER, *PNET_REQUEST_QUEUE_SET_DATA_HANDLER
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netrequestqueue.h
api_name: 
- NET_REQUEST_QUEUE_SET_DATA_HANDLER
targetos: Windows
---

# _NET_REQUEST_QUEUE_SET_DATA_HANDLER structure

## -description



Reserved for internal use. Call [NET_REQUEST_QUEUE_CONFIG_ADD_SET_DATA_HANDLER](nf-netrequestqueue-net_request_queue_config_add_set_data_handler.md) to add a caller-provided handler for a specific OID set request.

## -struct-fields

### -field Next
A pointer to the next custom handler.
 
### -field Memory
Reserved for internal use.
 
### -field Oid
Specifies the object identifier of the requested operation. The value is an OID\_*XXX* code. 
 
### -field EvtRequestSetData
A pointer to the client driver's implementation of an *[EVT_NET_REQUEST_SET_DATA](nc-netrequestqueue-evt_net_request_set_data.md)* event callback function.
 
### -field MinimumInputLength
The minimum input length needed by the client for this request.
 
### -field MinimumOutputLength
The minimum output length needed by the client for this request.

## -remarks


## -see-also
