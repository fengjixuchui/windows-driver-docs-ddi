---
UID: NF:netadapter.NetAdapterSetLinkLayerCapabilities
title: NetAdapterSetLinkLayerCapabilities function (netadapter.h)
description: Sets the link layer capabilities of the network adapter.
tech.root: netvista
ms.assetid: cf6bc60a-837a-44c1-bd8a-15ffb7c696a9
ms.date: 02/06/2018
ms.topic: function
f1_keywords:
 - "netadapter/NetAdapterSetLinkLayerCapabilities"
ms.keywords: NetAdapterSetLinkLayerCapabilities
req.header: netadapter.h
req.include-header: netadaptercx.h
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
req.typenames: NetAdapterSetLinkLayerCapabilities
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netadapter.h
api_name: 
- NetAdapterSetLinkLayerCapabilities
product:
- Windows
targetos: Windows
product:
- Windows
---

# NetAdapterSetLinkLayerCapabilities function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

Sets the link layer capabilities of the network adapter.

## -parameters

### -param Adapter
The network adapter object that the client created in a prior call to [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

### -param LinkLayerCapabilities
A pointer to an allocated and initialized [**NET_ADAPTER_LINK_LAYER_CAPABILITIES**](ns-netadapter-_net_adapter_link_layer_capabilities.md) structure.

## -returns
This method does not return a value.

## -remarks
The client driver calls this method when starting a net adapter, before calling [**NetAdapterStart**](nf-netadapter-netadapterstart.md).

This method, along with a few other set capability methods (see below), is the replacement for the [**NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES**](../ndis/ns-ndis-_ndis_miniport_adapter_general_attributes.md) union that a (non-WDF) client of Ndis.sys sets by calling [**NdisMSetMiniportAttributes**](../ndis/nf-ndis-ndismsetminiportattributes.md).



## -see-also

[**NetAdapterSetDataPathCapabilities**](nf-netadapter-netadaptersetdatapathcapabilities.md)

[**NetAdapterSetPowerCapabilities**](nf-netadapter-netadaptersetpowercapabilities.md)
