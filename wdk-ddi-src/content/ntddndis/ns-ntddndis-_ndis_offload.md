---
UID: NS:ntddndis._NDIS_OFFLOAD
title: _NDIS_OFFLOAD (ntddndis.h)
description: The NDIS_OFFLOAD structure specifies several computational tasks that can be offloaded to the network adapter.
old-location: netvista\ndis_offload.htm
tech.root: netvista
ms.assetid: 9d1447f1-aae8-4c27-a27b-e521c0c8ca97
ms.date: 02/27/2020
ms.keywords: "*PNDIS_OFFLOAD, IPSEC_OFFLOAD_V2_AND_TCP_CHECKSUM_COEXISTENCE, IPSEC_OFFLOAD_V2_AND_UDP_CHECKSUM_COEXISTENCE, NDIS_OFFLOAD, NDIS_OFFLOAD structure [Network Drivers Starting with Windows Vista], PNDIS_OFFLOAD, PNDIS_OFFLOAD structure pointer [Network Drivers Starting with Windows Vista], _NDIS_OFFLOAD, netvista.ndis_offload, ntddndis/NDIS_OFFLOAD, ntddndis/PNDIS_OFFLOAD, tcpip_offload_ref_e5f796e9-714c-43f9-98e4-1d0de0dcc8ee.xml"
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista,Supported in NDIS 6.0 and later.
req.target-min-winversvr: Windows Server 2008
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
targetos: Windows
req.typenames: NDIS_OFFLOAD, *PNDIS_OFFLOAD
f1_keywords:
 - _NDIS_OFFLOAD
 - ntddndis/_NDIS_OFFLOAD
 - PNDIS_OFFLOAD
 - ntddndis/PNDIS_OFFLOAD
 - NDIS_OFFLOAD
 - ntddndis/NDIS_OFFLOAD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - NDIS_OFFLOAD
---

# _NDIS_OFFLOAD structure


## -description

The NDIS_OFFLOAD structure specifies several computational <a href="https://docs.microsoft.com/windows-hardware/drivers/network/task-offload">tasks that can be offloaded to the network adapter</a>.

## -struct-fields

### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_OFFLOAD</b> structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_OFFLOAD.

Set the <b>Revision</b> and <b>Size</b> members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure as follows:

<ul>
<li>For NDIS 6.83 and later drivers:
<ul>
<li>Set <b>Revision</b> to NDIS_OFFLOAD_REVISION_6 (NDIS 6.83).</li>
<li> Set <b>Size</b> to NDIS_SIZEOF_NDIS_OFFLOAD_REVISION_6.</li>
</ul>
<li>For NDIS 6.70 and later drivers:<ul>
<li>Set <b>Revision</b> to NDIS_OFFLOAD_REVISION_5 (NDIS 6.70).</li>
<li>Set <b>Size</b> to NDIS_SIZEOF_NDIS_OFFLOAD_REVISION_5.</li>
</ul>
<li>For NDIS 6.50 and later drivers:<ul>
<li>Set <b>Revision</b> to NDIS_OFFLOAD_REVISION_4 (NDIS 6.50).</li>
<li>Set <b>Size</b> to NDIS_SIZEOF_NDIS_OFFLOAD_REVISION_4.</li>
</ul>
<li>For NDIS 6.30 and later drivers:<ul>
<li>Set <b>Revision</b> to NDIS_OFFLOAD_REVISION_3 (NDIS 6.30).</li>
<li>Set <b>Size</b> to NDIS_SIZEOF_NDIS_OFFLOAD_REVISION_3.</li>
</ul>
</li>
<li>For NDIS 6.1 and 6.20 drivers:<ul>
<li>Set <b>Revision</b> to NDIS_OFFLOAD_REVISION_2 (NDIS 6.1).</li>
<li>Set <b>Size</b> to NDIS_SIZEOF_NDIS_OFFLOAD_REVISION_2.</li>
</ul>
</li>
<li>For NDIS 6.0 drivers:<ul>
<li>Set <b>Revision</b> to NDIS_OFFLOAD_REVISION_1 (NDIS 6.0).</li>
<li>Set <b>Size</b> to NDIS_SIZEOF_NDIS_OFFLOAD_REVISION_1.</li>
</ul>
</li>
</ul>

### -field Checksum

Checksum offload information in an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_tcp_ip_checksum_offload">
     NDIS_TCP_IP_CHECKSUM_OFFLOAD</a> structure.

### -field LsoV1

Large send offload version 1 (LSOV1) information in an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_tcp_large_send_offload_v1">
     NDIS_TCP_LARGE_SEND_OFFLOAD_V1</a> structure.

### -field IPsecV1

Internet protocol security (IPsec) offload information in an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_ipsec_offload_v1">
     NDIS_IPSEC_OFFLOAD_V1</a> structure.

### -field LsoV2

Large send offload version 2 (LSOV2) offload information in an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_tcp_large_send_offload_v2">
     NDIS_TCP_LARGE_SEND_OFFLOAD_V2</a> structure.

### -field Flags

A bitwise OR  of flags that specify properties that the network adapter supports. The following flags are defined.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="IPSEC_OFFLOAD_V2_AND_TCP_CHECKSUM_COEXISTENCE"></a><a id="ipsec_offload_v2_and_tcp_checksum_coexistence"></a><dl>
<dt><b>IPSEC_OFFLOAD_V2_AND_TCP_CHECKSUM_COEXISTENCE</b></dt>
<dt>0x00000002</dt>
</dl>
</td>
<td width="60%">
The network adapter supports IPsecV2 and TCP checksums.

</td>
</tr>
<tr>
<td width="40%"><a id="IPSEC_OFFLOAD_V2_AND_UDP_CHECKSUM_COEXISTENCE"></a><a id="ipsec_offload_v2_and_udp_checksum_coexistence"></a><dl>
<dt><b>IPSEC_OFFLOAD_V2_AND_UDP_CHECKSUM_COEXISTENCE</b></dt>
<dt>0x00000004</dt>
</dl>
</td>
<td width="60%">
The network adapter supports IPsecV2 and UDP checksums.

</td>
</tr>
</table>

### -field IPsecV2

Internet protocol security (IPsec) offload version 2 information in an 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_ipsec_offload_v2">NDIS_IPSEC_OFFLOAD_V2</a> structure.

### -field Rsc

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/receive-segment-coalescing--rsc-">Receive Segment Coalescing (RSC)</a> offload information in    an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_tcp_recv_seg_coalesce_offload">NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD</a> structure.

### -field EncapsulatedPacketTaskOffloadGre

[Network Virtualization using Generic Routing Encapsulation (NVGRE) Task Offload](https://docs.microsoft.com/windows-hardware/drivers/network/network-virtualization-using-generic-routing-encapsulation--nvgre--task-offload) information in an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_encapsulated_packet_task_offload">NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD</a> structure. This member should only be set by miniport drivers that support task offloads for NVGRE-formatted packets.<div class="alert"><b>Note</b>  This member is available only in NDIS 6.30 and later. </div>
<div> </div>

### -field EncapsulatedPacketTaskOffloadVxlan

VXLAN encapsulated packet task offload information in an [**NDIS_ENCAPSULATED_PACKET_TASK_OFFLOAD_V2**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_encapsulated_packet_task_offload_v2) structure. This member should only be set by miniport drivers that support task offloads for VXLAN-formatted packets. VXLAN is similar to NVGRE, but with a different protocol.

<div class="alert"><b>Note</b>  This member is available only in NDIS 6.50 and later. </div>
<div> </div>

### -field EncapsulationTypes

The enabled encapsulation types for encapsulated packet task offload.

<div class="alert"><b>Note</b>  This member is available only in NDIS 6.50 and later. </div>
<div> </div>

### -field Rfc6877Xlat

464XLAT hardware offload information in an [**NDIS_RFC6877_464XLAT_OFFLOAD**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_rfc6877_464xlat_offload) structure.

<div class="alert"><b>Note</b>  This member is available only in NDIS 6.70 and later. </div>
<div> </div>

### -field UdpSegmentation

UDP Segmentation Offload (USO) hardware offload information in an [**NDIS_UDP_SEGMENTATION_OFFLOAD**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_offload) structure.

<div class="alert"><b>Note</b>  This member is available only in NDIS 6.83 and later. </div>
<div> </div>

## -remarks

The <b>NDIS_OFFLOAD</b> structure is used in the following places:<ul>
<li>The <b>DefaultOffloadConfiguration</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_adapter_offload_attributes">NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a> structure</li>
<li>The <b>DefaultOffloadConfiguration</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a> structure</li>
<li>The <b>DefaultOffloadConfiguration</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_filter_attach_parameters">NDIS_FILTER_ATTACH_PARAMETERS</a> structure</li>
<li>The <b>InformationBuffer</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure (which is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-tcp-offload-current-config">OID_TCP_OFFLOAD_CURRENT_CONFIG</a> OID request)</li>
<li>The <b>StatusBuffer</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-task-offload-current-config">NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a> status indication</li>
</ul>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/determining-the-rsc-capabilities-of-a-network-adapter">Determining the RSC Capabilities of a Network Adapter</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_filter_attach_parameters">NDIS_FILTER_ATTACH_PARAMETERS</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_ipsec_offload_v1">NDIS_IPSEC_OFFLOAD_V1</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_ipsec_offload_v2">NDIS_IPSEC_OFFLOAD_V2</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_adapter_offload_attributes">
   NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_status_indication">NDIS_STATUS_INDICATION</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-task-offload-current-config">
   NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_tcp_ip_checksum_offload">NDIS_TCP_IP_CHECKSUM_OFFLOAD</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_tcp_large_send_offload_v1">
   NDIS_TCP_LARGE_SEND_OFFLOAD_V1</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_tcp_large_send_offload_v2">
   NDIS_TCP_LARGE_SEND_OFFLOAD_V2</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_encapsulated_packet_task_offload">Network Virtualization using Generic Routing Encapsulation (NVGRE) Task Offload</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-offload-encapsulation">OID_OFFLOAD_ENCAPSULATION</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-tcp-offload-current-config">OID_TCP_OFFLOAD_CURRENT_CONFIG</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-tcp-connection-offload-hardware-capabilities">OID_TCP_OFFLOAD_HARDWARE_CAPABILITIES</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/task-offload">TCP/IP Task Offload</a>

[UDP Segmentation Offload (USO)](https://docs.microsoft.com/windows-hardware/drivers/network/udp-segmentation-offload-uso-)

