---
UID: NS:ntddndis._NDIS_TCP_LARGE_SEND_OFFLOAD_V1
title: _NDIS_TCP_LARGE_SEND_OFFLOAD_V1 (ntddndis.h)
description: The NDIS_TCP_LARGE_SEND_OFFLOAD_V1 structure provides large send offload version 1 (LSOV1) information in the NDIS_OFFLOAD structure.
old-location: netvista\ndis_tcp_large_send_offload_v1.htm
tech.root: netvista
ms.assetid: 3e26b6ae-15e1-41d5-b00d-3e09c1534413
ms.date: 05/02/2018
ms.keywords: "*PNDIS_TCP_LARGE_SEND_OFFLOAD_V1, NDIS_TCP_LARGE_SEND_OFFLOAD_V1, NDIS_TCP_LARGE_SEND_OFFLOAD_V1 structure [Network Drivers Starting with Windows Vista], PNDIS_TCP_LARGE_SEND_OFFLOAD_V1, PNDIS_TCP_LARGE_SEND_OFFLOAD_V1 structure pointer [Network Drivers Starting with Windows Vista], _NDIS_TCP_LARGE_SEND_OFFLOAD_V1, netvista.ndis_tcp_large_send_offload_v1, ntddndis/NDIS_TCP_LARGE_SEND_OFFLOAD_V1, ntddndis/PNDIS_TCP_LARGE_SEND_OFFLOAD_V1, tcpip_offload_ref_2a3bb0f8-f05b-462f-984d-774f607ee0da.xml"
ms.topic: struct
f1_keywords:
 - "ntddndis/NDIS_TCP_LARGE_SEND_OFFLOAD_V1"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddndis.h
api_name:
- NDIS_TCP_LARGE_SEND_OFFLOAD_V1
product:
- Windows
targetos: Windows
req.typenames: NDIS_TCP_LARGE_SEND_OFFLOAD_V1, *PNDIS_TCP_LARGE_SEND_OFFLOAD_V1
---

# _NDIS_TCP_LARGE_SEND_OFFLOAD_V1 structure


## -description


The NDIS_TCP_LARGE_SEND_OFFLOAD_V1 structure provides large send offload version 1 (LSOV1)
  information in the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_offload">NDIS_OFFLOAD</a> structure.


## -struct-fields




### -field IPv4

A structure within NDIS_TCP_LARGE_SEND_OFFLOAD_V1 that contains the following members:
     


### -field IPv4.Encapsulation

Encapsulation settings for IPv4. For more information about this member, see the following
       Remarks section.


### -field IPv4.MaxOffLoadSize

The maximum bytes of user data that the transport can pass to the miniport driver in a single
       packet. The transport will not pass a packet to the miniport driver that contains more user data bytes
       than 
       <b>MaxOffLoadSize</b> specifies. If such a packet must be transmitted, the transport itself segments
       the packet into smaller packets.


### -field IPv4.MinSegmentCount

The minimum number of segments that a large TCP packet must be divisible by before the transport
       can offload it to the hardware for segmentation. The transport will not offload a large packet to the
       miniport driver for segmentation unless the miniport driver can create at least as many segments as 
       <b>MinSegmentCount</b> specifies from the packet. If a large TCP packet does not meet the
       minimum-segment requirement, the TCP/IP transport itself segments the packet into smaller
       packets.


### -field IPv4.TcpOptions

A ULONG value that a miniport driver sets to indicate that the miniport driver can segment a
       large TCP packet whose TCP header contains TCP options or to indicate that this capability is enabled
       or disabled. The TCP/IP transport sets this value to enable or disable this capability.


### -field IPv4.IpOptions

A ULONG value that a miniport driver sets to indicate that a miniport adapter can segment a
       large TCP packet whose IP header contains IP options or to indicate that this capability is enabled or
       disabled.


## -remarks



The <b>NDIS_TCP_LARGE_SEND_OFFLOAD_V1</b> structure is used in the 
    <b>LsoV1</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_offload">NDIS_OFFLOAD</a> structure.
    <b>NDIS_TCP_LARGE_SEND_OFFLOAD_V1</b> specifies current or supported services that a miniport adapter provides
    for segmenting large TCP packets into smaller packets. NDIS also provides large send offload version 2
    (LSOV2), which is an enhanced version of LSO. For more information about LSOV2, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_tcp_large_send_offload_v2">
    NDIS_TCP_LARGE_SEND_OFFLOAD_V2</a>.


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_offload">NDIS_OFFLOAD</a> is used in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_adapter_offload_attributes">
    NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a> structure, 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a> structure, 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_filter_attach_parameters">
    NDIS_FILTER_ATTACH_PARAMETERS</a> structure, 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-tcp-offload-current-config">
    OID_TCP_OFFLOAD_CURRENT_CONFIG</a> OID, and the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-task-offload-current-config">
    NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a> status indication.

For 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-tcp-offload-current-config">OID_TCP_OFFLOAD_CURRENT_CONFIG</a>,
    the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_offload">NDIS_OFFLOAD</a> structure specifies the task offload capabilities that a miniport adapter supports. If
    the current offloads capabilities change, a miniport driver reports the new capabilities in an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-task-offload-current-config">
    NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a> status indication.

The 
    <b>Encapsulation</b> member of <b>NDIS_TCP_LARGE_SEND_OFFLOAD_V1</b> defines the LSOV1 encapsulation capabilities
    or settings for the miniport adapter.

In response to an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-tcp-offload-current-config">
    OID_TCP_OFFLOAD_CURRENT_CONFIG</a> query request, NDIS provides a bitwise OR of the encapsulation
    flags, which indicate the supported encapsulation settings, in the 
    <b>Encapsulation</b> member. Miniport drivers must provide Ethernet encapsulation
    (NDIS_ENCAPSULATION_IEEE_802_3). The other types of encapsulation are optional.

For an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-task-offload-current-config">
    NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a> status indication, the miniport driver provides a bitwise
    OR of the encapsulation flags, which indicate the current capabilities, in the 
    <b>Encapsulation</b> member.

The following flags are defined for the 
    <b>Encapsulation</b> member:

NDIS_ENCAPSULATION_NONE or NDIS_ENCAPSULATION_NOT_SUPPORTED  
Specifies that no encapsulation offload is supported.

NDIS_ENCAPSULATION_NULL  
Specifies NULL encapsulation.

NDIS_ENCAPSULATION_IEEE_802_3  
Specifies IEEE 802.3 encapsulation.

NDIS_ENCAPSULATION_IEEE_802_3_P_AND_Q  
Specifies IEEE 802.3p and IEEE 802.3q encapsulation.

NDIS_ENCAPSULATION_IEEE_802_3_P_AND_Q_IN_OOB  
Specifies that IEEE 802.3p and IEEE 802.3q encapsulation settings are specified in the NetBufferListInfo member of each NET_BUFFER_LIST structure.

NDIS_ENCAPSULATION_IEEE_LLC_SNAP_ROUTED  
Specifies logical link control (LLC) encapsulation for routed protocols, as described in RFC 1483. This flag is also used to indicate Ethernet LLC/SNAP encapsulation.

The values in the 
    <b>TcpOptions</b> and 
    <b>IpOptions</b> members of NDIS_TCP_LARGE_SEND_OFFLOAD_V1 specify miniport adapter support in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-tcp-offload-current-config">
    OID_TCP_OFFLOAD_CURRENT_CONFIG</a> OID or the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-task-offload-current-config">
    NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a> status indication. These members can have one of the
    following values:

NDIS_OFFLOAD_NOT_SUPPORTED  
The miniport adapter does not support the feature that the member specifies.

NDIS_OFFLOAD_SUPPORTED  
The miniport adapter supports the feature that the member specifies


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_filter_attach_parameters">NDIS_FILTER_ATTACH_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_adapter_offload_attributes">
   NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_offload">NDIS_OFFLOAD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-task-offload-current-config">
   NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_tcp_large_send_offload_v2">
   NDIS_TCP_LARGE_SEND_OFFLOAD_V2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-tcp-offload-current-config">OID_TCP_OFFLOAD_CURRENT_CONFIG</a>
 

 

