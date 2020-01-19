---
UID: NF:ndis.NdisMCmActivateVc
title: NdisMCmActivateVc function (ndis.h)
description: NdisMCmActivateVc notifies NDIS that an MCM driver is ready to make transfers on a particular VC.
old-location: netvista\ndismcmactivatevc.htm
tech.root: netvista
ms.assetid: 2c2e4f7d-578a-4429-baca-ebe45423afff
ms.date: 05/02/2018
ms.keywords: NdisMCmActivateVc, NdisMCmActivateVc function [Network Drivers Starting with Windows Vista], condis_mcm_ref_0dd062a7-dc2b-49c1-b319-e0189631e348.xml, ndis/NdisMCmActivateVc, netvista.ndismcmactivatevc
ms.topic: function
f1_keywords:
 - "ndis/NdisMCmActivateVc"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmActivateVc (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmActivateVc (NDIS 5.1)) in   Windows XP.
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisMCmActivateVc
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMCmActivateVc function


## -description


<b>NdisMCmActivateVc</b> notifies NDIS that an MCM driver is ready to make transfers on a particular
  VC.


## -parameters




### -param NdisVcHandle [in]

Specifies the handle identifying the VC.


### -param CallParameters [in]

Pointer to a caller-allocated buffer, formatted as a structure of type 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a>, containing all the
     media-specific parameters that the miniport driver uses for the activated VC.


## -returns



When 
     <b>NdisMCmActivateVc</b> returns anything other than NDIS_STATUS_PENDING, the MCM driver should make an
     internal call to its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_activate_vc_complete">
     ProtocolCmActivateVcComplete</a> function. Otherwise, NDIS calls the MCM driver's 
     <i>ProtocolCmActivateVcComplete</i> function when this operation is completed.




## -remarks



<b>NdisMCmActivateVc</b> informs NDIS that an MCM driver has set up call and media parameters on a newly
    created VC or changed the call parameters on an established VC.

An MCM driver must call 
    <b>NdisMCmActivateVc</b> after establishing a connection on a VC but before any data is sent or received
    on that VC. This call notifies NDIS that the miniport driver has made a NIC ready for transfers on the
    VC.

For a client-initiated outgoing call, an MCM driver usually calls 
    <b>NdisMCmActivateVc</b> following the handshake denoting a negotiated agreement with the remote node or
    successful call-setup at the switch, before it notifies NDIS (and the client) of outgoing call completion
    with 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmmakecallcomplete">NdisMCmMakeCallComplete</a>. For an
    incoming call, an MCM driver usually calls 
    <b>NdisMCmActivateVc</b> after it has called 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmcreatevc">NdisMCmCreateVc</a> successfully and before it
    calls 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdispatchincomingcall">
    NdisMCmDispatchIncomingCall</a>.

The driver writer determines whether an MCM driver has an (internal) 
    <i>MiniportCoActivateVc</i> function that the driver calls in the context of setting up connections for
    outgoing and incoming calls.

For the duration of the connection, an MCM driver can modify the call parameters as conditions on the
    network change and/or whenever the client calls 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclmodifycallqos">NdisClModifyCallQoS</a>. The MCM driver
    must update the state that it maintains about call parameters to the new values if it can continue to
    make transfers on the VC according to the newly modified call parameters. It must call 
    <b>NdisMCmActivateVc</b> to notify NDIS of any changes in the call parameters for the active VC.
    Otherwise, the MCM driver can do either of the following:

<ul>
<li>
Call 
      <b>NdisMCmDeactivateVc</b> after failing the client's request to modify QoS or other call parameters for
      the VC to such a state that the miniport driver cannot continue to make transfers on the VC.

</li>
<li>
Restore the call parameters to a previously accepted state, notify the client that requested the
      change, and remain ready to continue transferring data on the VC. In this case, the client has the
      option of accepting the restored call parameters or rejecting them and initiating a close of the
      VC.

</li>
</ul>
Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmActivateVc</b>. Stand-alone call managers, which register themselves with NDIS as protocol
    drivers, call 
    <b>NdisCmActivateVc</b> instead.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_activate_vc">MiniportCoActivateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclmakecall">NdisClMakeCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclmodifycallqos">NdisClModifyCallQoS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmactivatevc">NdisCmActivateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmcreatevc">NdisMCmCreateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdeactivatevc">NdisMCmDeactivateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdispatchincomingcall">NdisMCmDispatchIncomingCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a>
 

 

