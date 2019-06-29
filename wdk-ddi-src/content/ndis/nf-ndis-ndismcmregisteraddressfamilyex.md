---
UID: NF:ndis.NdisMCmRegisterAddressFamilyEx
title: NdisMCmRegisterAddressFamilyEx function (ndis.h)
description: The NdisMCmRegisterAddressFamilyEx function registers an address family (AF) for communication between a miniport call manager (MCM) and CoNDIS clients.
old-location: netvista\ndismcmregisteraddressfamilyex.htm
tech.root: netvista
ms.assetid: f58a9c08-d2cf-48d1-98d1-68aecd3b7bd0
ms.date: 05/02/2018
ms.keywords: NdisMCmRegisterAddressFamilyEx, NdisMCmRegisterAddressFamilyEx function [Network Drivers Starting with Windows Vista], condis_mcm_ref_9e0ef0aa-0fa8-4f40-a225-8908099356bc.xml, ndis/NdisMCmRegisterAddressFamilyEx, netvista.ndismcmregisteraddressfamilyex
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_MCM_Function
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
- NdisMCmRegisterAddressFamilyEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMCmRegisterAddressFamilyEx function


## -description


The
  <b>NdisMCmRegisterAddressFamilyEx</b> function registers an address family (AF) for communication between a
  miniport call manager (MCM) and CoNDIS clients.


## -parameters




### -param MiniportAdapterHandle [in]

An NDIS-supplied handle that identifies a miniport adapter. This handle is an input parameter to
     the MCM's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">
     MiniportInitializeEx</a> function.


### -param AddressFamily [in]

A pointer to a 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545368(v=vs.85)">CO_ADDRESS_FAMILY</a> structure that identifies
     the AF that the MCM driver supports. 
     

The pointer becomes an input parameter to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_co_af_register_notify">
     ProtocolCoAfRegisterNotify</a> functions of all of the CoNDIS clients that are bound to this MCM
     driver.


## -returns



<b>NdisMCmRegisterAddressFamilyEx</b> can return any of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver registered with NDIS as a call manager for the AF that the 
       <i>AddressFamily</i> parameter specified, so NDIS will call the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_co_af_register_notify">
       ProtocolCoAfRegisterNotify</a> functions of all of the clients that bind to the MCM driver.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The requested operation failed because NDIS could not allocate sufficient memory or initialize
       the state information that it uses to track the MCM driver as a call manager of the specified
       AF.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
NDIS failed the call to 
       <b>NdisMCmRegisterAddressFamilyEx</b>, possibly for one of the following reasons:
       

<ul>
<li>
The caller was not registered as a connection-oriented miniport driver.

</li>
<li>
The caller tried to register a duplicate AF for a given miniport adapter.

</li>
</ul>
</td>
</tr>
</table>
 




## -remarks



NDIS MCMs, which register as NDIS miniport drivers by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismregisterminiportdriver">
    NdisMRegisterMiniportDriver</a> function, should call the 
    <b>NdisMCmRegisterAddressFamilyEx</b> function to register an AF. Stand-alone call managers should instead
    call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscmregisteraddressfamilyex">
    NdisCmRegisterAddressFamilyEx</a> function.

To register an AF for a miniport adapter, the MCM should call 
    <b>NdisMCmRegisterAddressFamilyEx</b> from the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function.

The driver of any network interface card (NIC) that has on-board connection-oriented signaling support
    can register itself as an MCM driver for better performance in managing calls. If a driver registers as
    an MCM driver, any stand-alone call manager with the NIC driver's own call-management support is
    displaced.

An MCM driver calls 
    <b>NdisMCmRegisterAddressFamilyEx</b> after it has determined that a NIC is fully operational and the
    driver can complete network I/O operations. That is, such an MCM registers itself as a call manager and
    advertises its specific signaling services for CoNDIS clients.

After 
    <i>MiniportInitializeEx</i> returns control with a successful registration as a call manager, NDIS calls
    the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a> functions
    of potential clients and, then, the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_co_af_register_notify">
    ProtocolCoAfRegisterNotify</a> functions of all of the clients that bind themselves to the associated
    MCM miniport adapter. These clients then cause NDIS to call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cm_open_af">ProtocolCmOpenAf</a> function of the
    MCM.

An MCM can support more than one AF for a single NIC that it manages. The MCM driver must call 
    <b>NdisMCmRegisterAddressFamilyEx</b> once for each AF that it registers for a miniport adapter. Only one
    MCM driver can support a particular type of AF for clients that are bound to a given miniport
    adapter.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545368(v=vs.85)">CO_ADDRESS_FAMILY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscmregisteraddressfamilyex">
   NdisCmRegisterAddressFamilyEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cm_open_af">ProtocolCmOpenAf</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_co_af_register_notify">ProtocolCoAfRegisterNotify</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_co_delete_vc">ProtocolCoDeleteVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_co_oid_request">ProtocolCoOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_co_oid_request_complete">
   ProtocolCoOidRequestComplete</a>
 

 

