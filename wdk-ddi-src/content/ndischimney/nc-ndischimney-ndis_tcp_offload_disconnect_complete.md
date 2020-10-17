---
UID: NC:ndischimney.NDIS_TCP_OFFLOAD_DISCONNECT_COMPLETE
title: NDIS_TCP_OFFLOAD_DISCONNECT_COMPLETE (ndischimney.h)
description: An offload target calls the NdisTcpOffloadDisconnectComplete function to complete a disconnect request that was initiated by a previous call to the MiniportTcpOffloadDisconnect function of the offload target.
old-location: netvista\ndistcpoffloaddisconnectcomplete.htm
tech.root: netvista
ms.assetid: e862d9fe-a60c-4397-95ce-62aa1ef17eae
ms.date: 05/02/2018
keywords: ["NDIS_TCP_OFFLOAD_DISCONNECT_COMPLETE callback function"]
ms.keywords: NDIS_TCP_OFFLOAD_DISCONNECT_COMPLETE, NDIS_TCP_OFFLOAD_DISCONNECT_COMPLETE callback, NdisTcpOffloadDisconnectComplete, NdisTcpOffloadDisconnectComplete callback function [Network Drivers Starting with Windows Vista], ndischimney/NdisTcpOffloadDisconnectComplete, netvista.ndistcpoffloaddisconnectcomplete, tcp_chim_ndis_func_4a062983-d7c0-47c4-9eeb-dd3561c6b31a.xml
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.typenames: 
f1_keywords:
 - NDIS_TCP_OFFLOAD_DISCONNECT_COMPLETE
 - ndischimney/NDIS_TCP_OFFLOAD_DISCONNECT_COMPLETE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ndischimney.h
api_name:
 - NdisTcpOffloadDisconnectComplete
---

# NDIS_TCP_OFFLOAD_DISCONNECT_COMPLETE callback function


## -description

<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

An offload target calls the 
  <b>NdisTcpOffloadDisconnectComplete</b> function to complete a disconnect request that was initiated by a
  previous call to the 
  <a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_disconnect_handler">
  MiniportTcpOffloadDisconnect</a> function of the offload target.

## -parameters

### -param NdisMiniportHandle 

[in]
The handle that the offload target obtained in a previous call to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">
     NdisMRegisterMiniportDriver</a> function.

### -param NetBufferList 

[in]
A pointer to a single 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure. The offload
     target obtained this pointer as an input parameter to its 
     <a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_disconnect_handler">
     MiniportTcpOffloadDisconnect</a> function.

## -remarks

<b>Completing an Abortive Disconnect
    </b>

If the offload target issued an abortive disconnect, it must do the following before calling the 
    <b>NdisTcpOffloadDisconnectComplete</b> function:

<ul>
<li>
Complete all outstanding send requests on the connection with a status value of
      NDIS_STATUS_REQUEST_ABORTED. The offload target writes this status value to the 
      <b>Status</b> member of each NET_BUFFER_LIST structure in the linked list that it passes to the 
      <a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_send_complete">
      NdisTcpOffloadSendComplete</a> function.

</li>
<li>
Write a status value to the 
      <b>Status</b> member of the NET_BUFFER_LIST structure pointed to by the 
      <i>NetBufferList</i> pointer. A status value of NDIS_STATUS_SUCCESS indicates that the offload target
      successfully sent the RST segment. For a description of the allowable status values, see 
      <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>.

</li>
</ul>
<b>Completing a Graceful Disconnect
    </b>

Before completing a graceful disconnect request, the offload target must:

<ul>
<li>
Write a status value to the 
      <b>Status</b> member of the NET_BUFFER_LIST structure that it passes to the 
      <b>
      NdisTcpOffloadDisconnectComplete</b> function:

<ul>
<li>A value of NDIS_STATUS_SUCCESS indicates that the FIN segment, as well as any user data, was
       successfully sent by the offload target 
       <u>and</u> was also acknowledged by the remote host.</li>
<li>A value of NDIS_STATUS_UPLOAD_IN_PROGRESS indicates that the TCP connection referenced by 
       <i>NdisMiniportHandle</i> is being uploaded.</li>
<li>A value of NDIS_STATUS_REQUEST_ABORTED indicates that the FIN segment and/or any user data were
       not successfully transmitted by the offload target and acknowledged by the remote host. The host stack
       will eventually terminate the offload of the TCP connection.</li>
</ul>
</li>
<li>
Specify the number of user data bytes that were sent and successfully acknowledged. The offload
      target does this by calling the 
      <a href="/windows-hardware/drivers/network/net-buffer-list-info">NET_BUFFER_LIST_INFO</a> macro with an 
      <i>id</i> of 
      <b>TcpOffloadBytesTransferred</b>.

</li>
<li>
Call the 
      <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisadvancenetbufferdatastart">
      NdisAdvanceNetBufferDataStart</a> function. The 
      <i>NetBufferList</i> parameter should point to the NET_BUFFER structure associated with the
      NET_BUFFER_LIST structure that the offload target passes to the 
      <b>NdisTcpOffloadDisconnectComplete</b> function. The 
      <i>DataOffsetDelta</i> parameter should specify the number of data bytes from the NET_BUFFER structure
      that were both transmitted by the offload target and also successfully acknowledged by the remote host.
      The 
      <i>FreeMdl</i> parameter should be <b>NULL</b>.

</li>
</ul>
Note that the 
    <b>NdisTcpOffloadDisconnectComplete</b> function returns only the NET_BUFFER_LIST structure and associated
    structures that NDIS passed to the offload target's 
    <a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_disconnect_handler">
    MiniportTcpOffloadDisconnect</a> function. The 
    <b>NdisTcpOffloadDisconnectComplete</b> function cannot return NET_BUFFER_LIST structures that NDIS passed
    in previous calls to the offload target's 
    <a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_send_handler">
    MiniportTcpOffloadSend</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_disconnect_handler">
   MiniportTcpOffloadDisconnect</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/network/net-buffer-list-info">NET_BUFFER_LIST_INFO</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisadvancenetbufferdatastart">
   NdisAdvanceNetBufferDataStart</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>



<a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_send_complete">NdisTcpOffloadSendComplete</a>