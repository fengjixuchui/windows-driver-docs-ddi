---
UID: NF:ndis.NdisReEnumerateProtocolBindings
title: NdisReEnumerateProtocolBindings function (ndis.h)
description: The NdisReEnumerateProtocolBindings function causes NDIS to call a protocol driver's ProtocolBindAdapterEx function one time for each miniport adapter for which the driver is configured to bind but to which the driver is not currently bound.
old-location: netvista\ndisreenumerateprotocolbindings.htm
tech.root: netvista
ms.assetid: e47d812b-2fbb-44c4-a441-bd30ae89a5eb
ms.date: 05/02/2018
ms.keywords: NdisReEnumerateProtocolBindings, NdisReEnumerateProtocolBindings function [Network Drivers Starting with Windows Vista], ndis/NdisReEnumerateProtocolBindings, netvista.ndisreenumerateprotocolbindings, protocol_ndis_functions_ref_097465b9-b6e9-435a-8ac4-6d302363e946.xml
ms.topic: function
f1_keywords:
 - "ndis/NdisReEnumerateProtocolBindings"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisReEnumerateProtocolBindings (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisReEnumerateProtocolBindings (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function, NdisReEnumerateProtocolBindings
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisReEnumerateProtocolBindings
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisReEnumerateProtocolBindings function


## -description


The 
  <b>NdisReEnumerateProtocolBindings</b> function causes NDIS to call a protocol driver's 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a> function one
  time for each miniport adapter for which the driver is configured to bind but to which the driver is not
  currently bound.


## -parameters




### -param NdisProtocolHandle [in]

A handle representing the calling protocol driver. The driver obtained this handle with a previous
     call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisregisterprotocoldriver">
     NdisRegisterProtocolDriver</a> function.


## -returns



None




## -remarks



A protocol driver can call the 
    <b>NdisReEnumerateProtocolBindings</b> function to rebind to one or more miniport adapters.

Protocol drivers cannot call 
    <b>NdisReEnumerateProtocolBindings</b> from within the context of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>, or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_unbind_adapter_ex">
    ProtocolUnbindAdapterEx</a> functions. Also, protocol drivers cannot call 
    <b>NdisReEnumerateProtocolBindings</b> from within the context of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a> function if the    
    <i>ProtocolBindingContext</i> parameter of 
    <i>ProtocolNetPnPEvent</i> is not <b>NULL</b>. However, protocol drivers can call 
    <b>NdisReEnumerateProtocolBindings</b> from within the context of 
    <i>ProtocolNetPnPEvent</i> if 
    <i>ProtocolBindingContext</i> is <b>NULL</b>. A <b>NULL</b><i>ProtocolBindingContext</i> value indicates that the event applies to all bindings.

NDIS might complete the binding operations after the call to 
    <b>NdisReEnumerateProtocolBindings</b> returns. That is, NDIS might complete bindings to the miniport
    adapters for which the protocol driver is configured to bind but to which the protocol driver is not
    currently bound at a later time.

An intermediate driver should call 
    <b>NdisReEnumerateProtocolBindings</b> after its 
    <i>ProtocolNetPnPEvent</i> function receives 
    <b>NetEventReconfigure</b> on a <b>NULL</b><i>ProtocolBindingContext</i> . NDIS then calls the driver's 
    <i>ProtocolBindAdapterEx</i> function one time for each miniport adapter for which the driver is
    configured to bind but to which the driver is not currently bound.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff550472(v=vs.85)">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisregisterprotocoldriver">NdisRegisterProtocolDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_unbind_adapter_ex">ProtocolUnbindAdapterEx</a>
 

 

