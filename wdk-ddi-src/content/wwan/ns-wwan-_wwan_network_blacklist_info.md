---
UID: NS:wwan._WWAN_NETWORK_BLACKLIST_INFO
title: _WWAN_NETWORK_BLACKLIST_INFO (wwan.h)
description: The WWAN_NETWORK_BLACKLIST_INFO structure contains a list of network blacklists for a mobile broadband (MBB) modem.
tech.root: netvista
ms.assetid: 3506024c-79e1-4603-a7a8-a9ed1aae0372
ms.date: 08/21/2018
keywords: ["WWAN_NETWORK_BLACKLIST_INFO structure"]
ms.keywords: _WWAN_NETWORK_BLACKLIST_INFO, WWAN_NETWORK_BLACKLIST_INFO, *PWWAN_NETWORK_BLACKLIST_INFO,
req.header: wwan.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: WWAN_NETWORK_BLACKLIST_INFO, *PWWAN_NETWORK_BLACKLIST_INFO
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _WWAN_NETWORK_BLACKLIST_INFO
 - wwan/_WWAN_NETWORK_BLACKLIST_INFO
 - PWWAN_NETWORK_BLACKLIST_INFO
 - wwan/PWWAN_NETWORK_BLACKLIST_INFO
 - WWAN_NETWORK_BLACKLIST_INFO
 - wwan/WWAN_NETWORK_BLACKLIST_INFO
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_NETWORK_BLACKLIST_INFO
product:
 - Windows
---

# _WWAN_NETWORK_BLACKLIST_INFO structure


## -description

> [!IMPORTANT]
> ### Bias-free communication
>
> Microsoft supports a diverse and inclusive environment. This article contains references to terminology that the Microsoft [style guide for bias-free communication](/style-guide/bias-free-communication) recognizes as exclusionary. The word or phrase is used in this article for consistency because it currently appears in the software. When the software is updated to remove the language, this article will be updated to be in alignment.

The **WWAN_NETWORK_BLACKLIST_INFO** structure contains a list of network blacklist providers for a mobile broadband (MBB) modem.

## -struct-fields

### -field BlacklistState

A [**WWAN_NETWORK_BLACKLIST_STATE**](ne-wwan-_wwan_network_blacklist_state.md) value that indicates whether any of the blacklist conditions are met that result in the modem not registering with the network.

### -field BlacklistProviderList

 
A [**WWAN_LIST_HEADER**](ns-wwan-_wwan_list_header.md) structure that represents a list of network blacklists. The **ElementType** member in the **WWAN_LIST_HEADER** should be set to **WwanStructNetworkBlacklistProvider**. The **ElementCount** member in the **WWAN_LIST_HEADER** should be set to the number of [**WWAN_NETWORK_BLACKLIST_PROVIDER**](ns-wwan-_wwan_network_blacklist_provider.md) structures that follow the **WWAN_LIST_HEADER** structure.

## -remarks

This structure is used in the [**NDIS_WWAN_SET_NETWORK_BLACKLIST**](../ndiswwan/ns-ndiswwan-_ndis_wwan_set_network_blacklist.md) structure and the [**NDIS_WWAN_NETWORK_BLACKLIST**](../ndiswwan/ns-ndiswwan-_ndis_wwan_network_blacklist.md) structure.

## -see-also

[MB Network Blacklist Operations](/windows-hardware/drivers/network/mb-network-blacklist-operations)

[OID_WWAN_NETWORK_BLACKLIST](/windows-hardware/drivers/network/oid-wwan-network-blacklist)

[**NDIS_WWAN_SET_NETWORK_BLACKLIST**](../ndiswwan/ns-ndiswwan-_ndis_wwan_set_network_blacklist.md)

[**NDIS_WWAN_NETWORK_BLACKLIST**](../ndiswwan/ns-ndiswwan-_ndis_wwan_network_blacklist.md)

[**WWAN_NETWORK_BLACKLIST_STATE**](ne-wwan-_wwan_network_blacklist_state.md)

[**WWAN_NETWORK_BLACKLIST_PROVIDER**](ns-wwan-_wwan_network_blacklist_provider.md)

[**WWAN_LIST_HEADER**](ns-wwan-_wwan_list_header.md)