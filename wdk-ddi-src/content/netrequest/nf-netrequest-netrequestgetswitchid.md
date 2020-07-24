---
UID: NF:netrequest.NetRequestGetSwitchId
title: NetRequestGetSwitchId function (netrequest.h)
description: Retrieves the switch identifier for the net request.
tech.root: netvista
ms.assetid: 44e290cf-13ea-4da5-898a-4a882eb881bf
ms.date: 02/08/2018
keywords: ["NetRequestGetSwitchId function"]
f1_keywords:
 - "netrequest/NetRequestGetSwitchId"
 - "NetRequestGetSwitchId"
ms.keywords: NetRequestGetSwitchId
req.header: netrequest.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib:
req.dll:
req.irql: <= DISPATCH_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
req.alt-api:
req.alt-loc:
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netrequest.h
api_name: 
- NetRequestGetSwitchId
targetos: Windows
---

# NetRequestGetSwitchId function


## -description



Retrieves the switch identifier for the net request.

## -parameters

### -param Request
A handle to a network request object.

## -returns
Returns an NDIS_NIC_SWITCH_ID value that specifies a switch identifier. The switch identifier is an integer between zero and the number of switches that the network adapter supports. An NDIS_DEFAULT_SWITCH_ID value indicates the default network adapter switch. 

## -remarks


## -see-also

[NDIS_NIC_SWITCH_PARAMETERS](../ntddndis/ns-ntddndis-_ndis_nic_switch_parameters.md)
