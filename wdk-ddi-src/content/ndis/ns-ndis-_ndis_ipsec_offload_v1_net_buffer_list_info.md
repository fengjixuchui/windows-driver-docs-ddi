---
UID: NS:ndis._NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO
title: _NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO (ndis.h)
description: The NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO structure specifies information that is used in offloading Internet protocol security (IPsec) tasks from the TCP/IP transport to a miniport driver.
old-location: netvista\ndis_ipsec_offload_v1_net_buffer_list_info.htm
tech.root: netvista
ms.assetid: 990b3df6-5ef7-4201-a09d-d94822d0a8bb
ms.date: 05/02/2018
keywords: ["NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO structure"]
ms.keywords: "*PNDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO, CRYPTO_GENERIC_ERROR, CRYPTO_INVALID_PACKET_SYNTAX, CRYPTO_INVALID_PROTOCOL, CRYPTO_SUCCESS, CRYPTO_TRANSPORT_AH_AUTH_FAILED, CRYPTO_TRANSPORT_ESP_AUTH_FAILED, CRYPTO_TUNNEL_AH_AUTH_FAILED, CRYPTO_TUNNEL_ESP_AUTH_FAILED, NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO, NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO, PNDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO, ndis/NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO, ndis/PNDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO, netvista.ndis_ipsec_offload_v1_net_buffer_list_info, tcpip_offload_ref_2e052bb5-6546-47a9-b51b-f1f77116835d.xml"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0. For NDIS 6.1 and later, use NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO.
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
targetos: Windows
req.typenames: NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO, *PNDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO
f1_keywords:
 - _NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO
 - ndis/_NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO
 - PNDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO
 - ndis/PNDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO
 - NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO
 - ndis/NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO
---

# _NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO structure


## -description

The <b>NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO</b> structure specifies information that is used in
  offloading Internet protocol security (IPsec) tasks from the TCP/IP transport to a miniport driver.

## -struct-fields

### -field Transmit

A structure that contains the following members:

### -field Transmit.OffloadHandle

A handle to the outbound security association (SA) for a packet that has just one IPsec payload,
       regardless of whether that payload is for a transport (end-to-end) connection or a tunnel
       connection.

### -field Receive

A structure that contains the following members:

### -field Receive.SaDeleteReq

A USHORT value that, when set, indicates that the TCP/IP transport should issue the 
       <a href="/previous-versions/windows/embedded/gg155485(v=winembedded.80)">
       OID_TCP_TASK_IPSEC_DELETE_SA</a> OID once to delete the inbound SA that the packet was received over
       and once again to delete the outbound SA that corresponds to the deleted inbound SA. The network
       interface card (NIC) must not remove either of these SAs before it receives the corresponding
       OID_TCP_TASK_IPSEC_DELETE_SA request.

### -field Receive.CryptoDone

A USHORT value that, when set, indicates that a NIC performed IPsec checking on at least one
       IPsec payload in the receive packet. When this value is cleared, it indicates that the NIC did not
       perform IPsec checking on the packet.

### -field Receive.NextCryptoDone

A USHORT value that, when set, indicates that a NIC performed IPsec checking on both the tunnel
       and transport portions of the receive packet. 
       <b>CryptoDone</b> must also be set in this case. 
       <b>NextCryptoDone</b> is set only if a packet has both tunnel and transport IPsec payloads; otherwise, 
       <b>NextCryptoDone</b> is set to zero.

### -field Receive.Pad

Reserved for NDIS.

### -field Receive.CryptoStatus

The result of IPsec checking that a NIC performed on a receive packet. This result can be
       described as one of the following values:
       

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="___________CRYPTO_SUCCESS"></a><a id="___________crypto_success"></a><dl>
<dt><b>
          CRYPTO_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The packet was successfully decrypted, if necessary, and the authentication header (AH)
         checksums, encapsulating security payload (ESP) checksums, or both checksums in the packet were
         validated.

</td>
</tr>
<tr>
<td width="40%"><a id="___________CRYPTO_GENERIC_ERROR"></a><a id="___________crypto_generic_error"></a><dl>
<dt><b>
          CRYPTO_GENERIC_ERROR</b></dt>
</dl>
</td>
<td width="60%">
The packet failed the IPsec check for an unspecified reason.

</td>
</tr>
<tr>
<td width="40%"><a id="___________CRYPTO_TRANSPORT_AH_AUTH_FAILED"></a><a id="___________crypto_transport_ah_auth_failed"></a><dl>
<dt><b>
          CRYPTO_TRANSPORT_AH_AUTH_FAILED</b></dt>
</dl>
</td>
<td width="60%">
The AH checksum for the transport portion of the packet was invalid.

</td>
</tr>
<tr>
<td width="40%"><a id="___________CRYPTO_TRANSPORT_ESP_AUTH_FAILED"></a><a id="___________crypto_transport_esp_auth_failed"></a><dl>
<dt><b>
          CRYPTO_TRANSPORT_ESP_AUTH_FAILED</b></dt>
</dl>
</td>
<td width="60%">
The ESP checksum for the transport portion of the packet was invalid.

</td>
</tr>
<tr>
<td width="40%"><a id="___________CRYPTO_TUNNEL_AH_AUTH_FAILED"></a><a id="___________crypto_tunnel_ah_auth_failed"></a><dl>
<dt><b>
          CRYPTO_TUNNEL_AH_AUTH_FAILED</b></dt>
</dl>
</td>
<td width="60%">
The AH checksum for the tunnel portion of the packet was invalid.

</td>
</tr>
<tr>
<td width="40%"><a id="___________CRYPTO_TUNNEL_ESP_AUTH_FAILED"></a><a id="___________crypto_tunnel_esp_auth_failed"></a><dl>
<dt><b>
          CRYPTO_TUNNEL_ESP_AUTH_FAILED</b></dt>
</dl>
</td>
<td width="60%">
The ESP checksum for the tunnel portion of the packet was invalid.

</td>
</tr>
<tr>
<td width="40%"><a id="___________CRYPTO_INVALID_PACKET_SYNTAX"></a><a id="___________crypto_invalid_packet_syntax"></a><dl>
<dt><b>
          CRYPTO_INVALID_PACKET_SYNTAX</b></dt>
</dl>
</td>
<td width="60%">
The receive packet's length is invalid.

</td>
</tr>
<tr>
<td width="40%"><a id="___________CRYPTO_INVALID_PROTOCOL"></a><a id="___________crypto_invalid_protocol"></a><dl>
<dt><b>
          CRYPTO_INVALID_PROTOCOL</b></dt>
</dl>
</td>
<td width="60%">
The IPsec protocols that were specified in the SA that the packet was received on do not match
         the IPsec protocols that were found in the packet. For example, this error occurs if the SA that the
         packet was received on specifies the AH protocol but the packet contained only an ESP header.

</td>
</tr>
</table>

## -remarks

Before the TCP/IP transport passes a send packet that a NIC will perform IPsec tasks on to the
    miniport driver of the NIC, the transport updates the IPsec information in the
    <b>NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO</b> structure that is associated with the 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure.

Specifically, the TCP/IP transport supplies a value for the 
    <b>OffloadHandle</b> member in the <b>NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO</b> structure. The 
    <b>OffloadHandle</b> value specifies the handle to the outbound security association (SA) for a packet
    that has just one IPsec payload, regardless of whether that payload is for a transport (end-to-end)
    security association or a tunnel security association. The 
    <b>OffloadHandle</b> value that is supplied in the <b>NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO</b> structure
    has the same value as the 
    <b>OffloadHandle</b> value that the TCP/IP transport supplied when it set 
    <a href="/windows-hardware/drivers/network/oid-tcp-task-ipsec-add-sa">OID_TCP_TASK_IPSEC_ADD_SA</a> to request
    the miniport driver to add the outbound SA to the NIC.

Before a miniport driver indicates up a receive packet that has one or more IPsec payloads, the driver
    updates the <b>NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO</b> structure that is associated with the 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure as follows:

<ul>
<li>
If the NIC performed IPsec checks on at least one IPsec payload in the packet, the miniport driver
      sets the 
      <b>CryptoDone</b> member and indicates the results of the checksum validation tests by specifying the
      appropriate value in the 
      <b>CryptoStatus</b> member.

</li>
<li>
If the NIC performed IPsec checking on both the tunnel and transport portions of a receive packet,
      the miniport driver also sets the 
      <b>NextCryptoDone</b> member. 
      <b>NextCryptoDone</b> is set only if a packet has both tunnel and transport IPsec payloads; otherwise, 
      <b>NextCryptoDone</b> is set to zero.

</li>
<li>
If the NIC did not perform IPsec checks on the packet, the miniport driver does not set 
      <b>CryptoDone</b> or 
      <b>NextCryptoDone</b> and does not supply a 
      <b>CryptoStatus</b> value.

</li>
</ul>
To create space for another SA on the NIC, the miniport driver of the NIC can set 
    <b>SaDeleteReq</b> in the <b>NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO</b> structure for a receive packet. The
    TCP/IP transport subsequently issues 
    <a href="/previous-versions/windows/embedded/gg155485(v=winembedded.80)">OID_TCP_TASK_IPSEC_DELETE_SA</a> once
    to delete the inbound SA that the packet was received over and once again to delete the outbound SA that
    corresponds to the deleted inbound SA. The NIC must not remove either of these SAs before receiving the
    corresponding OID_TCP_TASK_IPSEC_DELETE_SA request. The miniport driver of the NIC can set 
    <b>SaDeleteReq</b> independently of 
    <b>CryptoDone</b> .

To set and get the IPsec information, use the 
    <b>IPsecOffloadV1NetBufferListInfo</b> index with the 
    <a href="/windows-hardware/drivers/network/net-buffer-list-info">NET_BUFFER_LIST_INFO</a> macro.
    <b>NET_BUFFER_LIST_INFO</b> returns the <b>NDIS_IPSEC_OFFLOAD_V1_NET_BUFFER_LIST_INFO</b> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_ipsec_offload_v2_net_buffer_list_info">NDIS_IPSEC_OFFLOAD_V2_NET_BUFFER_LIST_INFO</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/network/net-buffer-list-info">NET_BUFFER_LIST_INFO</a>



<a href="/windows-hardware/drivers/network/oid-tcp-task-ipsec-add-sa">OID_TCP_TASK_IPSEC_ADD_SA</a>



<a href="/previous-versions/windows/embedded/gg155485(v=winembedded.80)">OID_TCP_TASK_IPSEC_DELETE_SA</a>