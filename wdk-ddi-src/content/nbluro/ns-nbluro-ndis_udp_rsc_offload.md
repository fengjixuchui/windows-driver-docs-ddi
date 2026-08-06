---
UID: NS:nbluro._NDIS_UDP_RSC_OFFLOAD
tech.root: netvista
title: NDIS_UDP_RSC_OFFLOAD
ms.date: 01/18/2024
targetos: Windows
description: The NDIS_UDP_RSC_OFFLOAD structure contains the offload support state for UDP RSC (URO).
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ndis/nbluro.h
req.include-header: ndis.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: NDIS_UDP_RSC_OFFLOAD
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - nbluro.h
api_name:
 - _NDIS_UDP_RSC_OFFLOAD
 - NDIS_UDP_RSC_OFFLOAD
f1_keywords:
 - _NDIS_UDP_RSC_OFFLOAD
 - nbluro/_NDIS_UDP_RSC_OFFLOAD
 - NDIS_UDP_RSC_OFFLOAD
 - nbluro/NDIS_UDP_RSC_OFFLOAD
dev_langs:
 - c++
helpviewer_keywords:
 - _NDIS_UDP_RSC_OFFLOAD
---

## -description

The **NDIS_UDP_RSC_OFFLOAD** structure contains the offload support state for [UDP Receive Segment Coalescing Offload (URO)](/windows-hardware/drivers/network/udp-rsc-offload).

## -struct-fields

### -field Enabled

A BOOLEAN value that specifies whether UDP RSC offload is enabled.

## -remarks

A miniport driver advertises support for URO in the **UdpRsc** member of the [**NDIS_OFFLOAD**](../ntddndis/ns-ntddndis-_ndis_offload.md) structure that it passes to the [**NdisMSetMiniportAttributes**](../ndis/nf-ndis-ndismsetminiportattributes.md) function.

To determine if a miniport driver supports URO, NDIS drivers and other applications can query the [OID_TCP_OFFLOAD_HARDWARE_CAPABILITIES](/windows-hardware/drivers/network/oid-tcp-connection-offload-hardware-capabilities) OID which returns the **NDIS_OFFLOAD** structure.

## -see-also

[UDP Receive Segment Coalescing Offload (URO)](/windows-hardware/drivers/network/udp-rsc-offload)

[**NDIS_OFFLOAD**](../ntddndis/ns-ntddndis-_ndis_offload.md)

[OID_TCP_OFFLOAD_HARDWARE_CAPABILITIES](/windows-hardware/drivers/network/oid-tcp-connection-offload-hardware-capabilities)

[**NdisMSetMiniportAttributes**](../ndis/nf-ndis-ndismsetminiportattributes.md)