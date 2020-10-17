---
UID: NF:ndis.NdisClRegisterSap
title: NdisClRegisterSap function (ndis.h)
description: NdisClRegisterSap registers a SAP on which the client can receive incoming calls from a remote node.
old-location: netvista\ndisclregistersap.htm
tech.root: netvista
ms.assetid: 33ed0839-d1e3-4872-baa8-ead7e97f8c53
ms.date: 05/02/2018
keywords: ["NdisClRegisterSap function"]
ms.keywords: NdisClRegisterSap, NdisClRegisterSap function [Network Drivers Starting with Windows Vista], condis_client_ref_ee22bc25-7935-458f-8016-6537d9803acb.xml, ndis/NdisClRegisterSap, netvista.ndisclregistersap
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisClRegisterSap (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisClRegisterSap (NDIS 5.1)) in   Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Protocol_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisClRegisterSap
 - ndis/NdisClRegisterSap
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisClRegisterSap
---

# NdisClRegisterSap function


## -description

<b>NdisClRegisterSap</b> registers a SAP on which the client can receive incoming calls from a remote
  node.

## -parameters

### -param NdisAfHandle 

[in]
Specifies the handle returned by 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclopenaddressfamilyex">NdisClOpenAddressFamilyEx</a>,
     which implicitly identifies the call manager with which to register the SAP.

### -param ProtocolSapContext 

[in]
Specifies the handle to a caller-supplied resident context area in which the client maintains
     state for this SAP after it has been opened. NDIS passes this handle back to the client in all
     subsequent calls concerning this SAP if the call to 
     <b>NdisClRegisterSap</b> succeeds.

### -param Sap 

[in]
Pointer to a client-supplied specification for the SAP to be opened, formatted as a structure of
     type 
     <a href="/previous-versions/windows/hardware/network/ff545392(v=vs.85)">CO_SAP</a>.

### -param NdisSapHandle 

[out]
Pointer to a variable in which a handle to the newly registered SAP is returned if this call
     succeeds.

## -returns

When 
     <b>NdisClRegisterSap</b> returns anything other than NDIS_STATUS_PENDING, the client should make an
     internal call to its 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_register_sap_complete">
     ProtocolClRegisterSapComplete</a> function. Otherwise, NDIS calls the client's 
     <i>ProtocolClRegisterSapComplete</i> function when this operation is completed.

## -remarks

With a call to 
    <b>NdisClRegisterSap</b>, a client requests notifications of incoming calls on a particular SAP. NDIS
    forwards the given SAP information to the call manager's 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_reg_sap">ProtocolCmRegisterSap</a> function
    for validation. If the given SAP is already in use or if the call manager does not recognize the
    client-supplied specification at 
    <i>Sap</i>, the call manager fails this request.

SAP format is medium-dependent and specific to the address family supported by the call manager, which
    uses registered SAPs subsequently to route incoming calls to the appropriate client. A call manager can
    register SAPs for established PVCs without contacting other network components, depending on the
    underlying medium.

If its call to 
    <b>NdisClRegisterSap</b> succeeds, the client must save the handle returned at 
    <i>NdisSapHandle</i> because it is a required parameter to 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclderegistersap">NdisClDeregisterSap</a>. Callers of 
    <b>NdisClRegisterSap</b> usually pass a pointer to a variable in the client-allocated state area at 
    <i>ProtocolSapContext</i> so that NDIS can set it to the 
    <i>NdisSapHandle</i> if this call succeeds. NDIS passes the given 
    <i>ProtocolSapContext</i> to the client's registered ProtocolCl/Co<i>Xxx</i> functions in all subsequent calls concerning this SAP until the client calls 
    <b>NdisClDeregisterSap</b>.

Usually, a client calls 
    <b>NdisClRegisterSap</b> from its 
    <i>ProtocolAfRegisterNotify</i> function following its successful call to 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclopenaddressfamilyex">NdisClOpenAddressFamilyEx</a>.
    Registering one or more SAPs allows the client to receive its incoming call(s) as soon as the call
    manager receives them over the network.

By contrast with client-initiated outgoing calls, a client does not call 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscocreatevc">NdisCoCreateVc</a> before it calls 
    <b>NdisClRegisterSap</b>. For incoming calls, the call manager initiates the creation of the VC, as
    follows:

<ul>
<li>
On receipt of an incoming call on a registered SAP, the call manager first calls 
      <b>NdisCoCreateVc</b>, causing NDIS to call the client's 
      <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a> function.

</li>
<li>
When the VC has been set up and activated, the call manager calls 
      <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdispatchincomingcall">NdisCmDispatchIncomingCall</a>,
      causing NDIS to call the client's 
      <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_call">
      ProtocolClIncomingCall</a> function.

</li>
</ul>

## -see-also

<a href="/previous-versions/windows/hardware/network/ff545392(v=vs.85)">CO_SAP</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclderegistersap">NdisClDeregisterSap</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclmakecall">NdisClMakeCall</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdispatchincomingcall">NdisCmDispatchIncomingCall</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscocreatevc">NdisCoCreateVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_call">ProtocolClIncomingCall</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_register_sap_complete">
   ProtocolClRegisterSapComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_reg_sap">ProtocolCmRegisterSap</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_af_register_notify">ProtocolCoAfRegisterNotify</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a>