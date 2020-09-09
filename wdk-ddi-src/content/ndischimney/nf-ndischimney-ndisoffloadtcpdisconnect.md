---
UID: NF:ndischimney.NdisOffloadTcpDisconnect
title: NdisOffloadTcpDisconnect function (ndischimney.h)
description: A protocol or intermediate driver calls the NdisOffloadTcpDisconnect function to close the send half of an offloaded TCP connection.
old-location: netvista\ndisoffloadtcpdisconnect.htm
tech.root: netvista
ms.assetid: f8abff30-b641-4581-8532-8292993ca9f6
ms.date: 05/02/2018
keywords: ["NdisOffloadTcpDisconnect function"]
ms.keywords: NdisOffloadTcpDisconnect, NdisOffloadTcpDisconnect function [Network Drivers Starting with Windows Vista], ndischimney/NdisOffloadTcpDisconnect, netvista.ndisoffloadtcpdisconnect, tcp_chim_ndis_func_7b795689-321d-4d4f-992f-668d53bcf11b.xml
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
req.lib: Ndis.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisOffloadTcpDisconnect
 - ndischimney/NdisOffloadTcpDisconnect
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisOffloadTcpDisconnect
---

# NdisOffloadTcpDisconnect function


## -description

<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

A protocol or intermediate driver calls the 
  <b>NdisOffloadTcpDisconnect</b> function to close the send half of an offloaded TCP connection. In addition,
  if the disconnect to be performed is a graceful disconnect, the protocol or intermediate driver can supply
  application data that the underlying offload target must transmit on the offloaded TCP connection before it
  sends a FIN segment.

## -parameters

### -param NdisOffloadHandle 

[in]
A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_offload_handle">NDIS_OFFLOAD_HANDLE</a> structure in the
     caller's context for the offloaded TCP connection. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/referencing-offloaded-state-through-an-intermediate-driver">
     Referencing Offloaded State Through an Intermediate Driver</a>.

### -param NetBufferList 

[in]
A pointer to a single 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure. Only one 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure is associated with this
     NET_BUFFER_LIST structure.

### -param Flags 

[in]
As one of the following values, the type of disconnect to be performed:
     





#### TCP_DISCONNECT_ABORTIVE_CLOSE

Specifies that the offload target perform an abortive disconnect by sending an RST
       segment.



#### TCP_DISCONNECT_GRACEFUL_CLOSE

Specifies that the offload target perform a graceful disconnect by sending a FIN segment.

## -returns

The 
     <b>NdisOffloadTcpDisconnect</b> function always returns NDIS_STATUS_PENDING. The disconnect operation is
     always completed asynchronously.

## -remarks

In response to a call to its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_disconnect_handler">
    MiniportTcpOffloadDisconnect</a> function, an intermediate driver calls the 
    <b>NdisOffloadTcpDisconnect</b> function to propagate the disconnect operation to the underlying
    intermediate driver or offload target. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/propagating-i-o-operations">Propagating I/O Operations</a>.

To the 
    <b>NdisOffloadTcp<i>Xxx</i></b>
     function, the intermediate driver passes the following:

<ul>
<li>
An 
      <i>NdisOffloadHandle</i> function that references the NDIS_OFFLOAD_HANDLE structure stored in the
      intermediate driver's context for the offloaded TCP connection. For more information, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/referencing-offloaded-state-through-an-intermediate-driver">
      Referencing Offloaded State Through an Intermediate Driver</a>.

</li>
<li>
The same PNET_BUFFER_LIST pointer that NDIS passed to the intermediate driver's 
      <i>MiniportTcpOffloadDisconnect</i> function.

</li>
<li>
The same 
      <i>Flags</i> that NDIS passed to the intermediate driver's 
      <i>MiniportTcpOffloadDisconnect</i> function.

</li>
</ul>
When the underlying driver or offload target subsequently completes the disconnect operation by
    calling the 
    <b>NdisTcpOffloadDisconnectComplete</b> function, NDIS calls the intermediate driver's 
    <i>ProtocolOffloadDisconnectComplete</i> function. The intermediate driver then calls the 
    <b>NdisTcpOffloadDisconnectComplete</b> function to propagate the completion of the disconnect
    operation.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_disconnect_handler">
   MiniportTcpOffloadDisconnect</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_offload_handle">NDIS_OFFLOAD_HANDLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_disconnect_complete">
   NdisTcpOffloadDisconnectComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-tcp_offload_disconnect_complete_handler">
   ProtocolTcpOffloadDisconnectComplete</a>

