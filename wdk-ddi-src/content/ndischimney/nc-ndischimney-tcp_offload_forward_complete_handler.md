---
UID: NC:ndischimney.TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER
title: TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER (ndischimney.h)
description: NDIS calls a protocol or intermediate driver's ProtocolTcpOffloadForwardComplete function to complete a forward operation that the driver previously initiated by calling the NdisOffloadTcpForward function.
old-location: netvista\protocoltcpoffloadforwardcomplete.htm
tech.root: netvista
ms.assetid: 02a11841-d98a-4c74-8922-458826e2911e
ms.date: 05/02/2018
keywords: ["TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER callback function"]
ms.keywords: ProtocolTcpOffloadForwardComplete, ProtocolTcpOffloadForwardComplete callback function [Network Drivers Starting with Windows Vista], TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER, TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER callback, ndischimney/ProtocolTcpOffloadForwardComplete, netvista.protocoltcpoffloadforwardcomplete, tcp_chim_protocol_func_18981e3f-fec9-483d-b60e-54017ebd57d1.xml
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Windows
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
 - TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER
 - ndischimney/TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndischimney.h
api_name:
 - ProtocolTcpOffloadForwardComplete
---

# TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER callback function


## -description

<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls a protocol or intermediate driver's 
  <i>ProtocolTcpOffloadForwardComplete</i> function to complete a forward operation that the driver previously
  initiated by calling the 
  <a href="/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndisoffloadtcpdisconnect">
  NdisOffloadTcpForward</a> function.

## -parameters

### -param ProtocolBindingContext 

[in]
A handle to a context area allocated by the protocol driver. The driver maintains the per binding
     context information in this context area. The driver supplied this handle to NDIS when the driver called
     the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function.

### -param NetBufferList 

[in]
A pointer to a 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure. This structure
     can be stand-alone or the first structure in a linked list of NET_BUFFER_LIST structures. The driver
     supplied this pointer as an input parameter in a previous call to the 
     <b>NdisOffloadTcpForward</b> function.

## -remarks

In response to an underlying driver's or offload target's call to the 
    <b>NdisOffloadTcpForwardComplete</b> function, NDIS calls the overlying protocol driver's or intermediate
    driver's 
    <i>ProtocolTcpOffloadForwardComplete</i> function.

To propagate the completion of the forward operation to the overlying driver or host stack, the
    intermediate driver calls the 
    <b>NdisOffloadTcpForwardComplete</b> function, passing in the following:

<ul>
<li>
A 
      <i>ProtocolBindingContext</i>, which is a handle that uniquely identifies the intermediate driver.

</li>
<li>
The PNET_BUFFER_LIST pointer that NDIS passed to the intermediate driver's 
      <i>ProtocolTcpOffloadForwardComplete</i> function.

</li>
</ul>
In response, NDIS calls the overlying driver's or host stack's 
    <i>ProtocolTcpOffloadForwardComplete</i> function, passing in a 
    <i>ProtocolBindingContext</i> handle and the PNET_BUFFER_LIST pointer supplied by the intermediate driver
    to the 
    <b>NdisOffloadTcpForwardComplete</b> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_forward_handler">MiniportTcpOffloadForward</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndisoffloadtcpforward">NdisOffloadTcpForward</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_forward_complete">
   NdisTcpOffloadForwardComplete</a>