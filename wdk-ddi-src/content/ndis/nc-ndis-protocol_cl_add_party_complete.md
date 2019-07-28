---
UID: NC:ndis.PROTOCOL_CL_ADD_PARTY_COMPLETE
title: PROTOCOL_CL_ADD_PARTY_COMPLETE (ndis.h)
description: The ProtocolClAddPartyComplete function is required for connection-oriented NDIS clients that set up multipoint connections.
old-location: netvista\protocolcladdpartycomplete.htm
tech.root: netvista
ms.assetid: ea3ebbe9-fd94-44b8-8801-639d099c5158
ms.date: 05/02/2018
ms.keywords: PROTOCOL_CL_ADD_PARTY_COMPLETE, PROTOCOL_CL_ADD_PARTY_COMPLETE callback, ProtocolClAddPartyComplete, ProtocolClAddPartyComplete callback function [Network Drivers Starting with Windows Vista], condis_client_ref_9c69b521-649f-4c2b-b665-e79cd8c07e48.xml, ndis/ProtocolClAddPartyComplete, netvista.protocolcladdpartycomplete
ms.topic: callback
f1_keywords:
 - "ndis/ProtocolClAddPartyComplete"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolClAddPartyComplete   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolClAddPartyComplete   (NDIS 5.1)) in Windows XP.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- ProtocolClAddPartyComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# PROTOCOL_CL_ADD_PARTY_COMPLETE callback function


## -description


The 
  <i>ProtocolClAddPartyComplete</i> function is required for connection-oriented NDIS clients that set up
  multipoint connections. Such clients must have 
  <i>ProtocolClAddPartyComplete</i> functions to complete the asynchronous operations that they initiate with 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscladdparty">NdisClAddParty</a>. Otherwise, such a protocol
  driver's registered 
  <i>ProtocolClAddPartyComplete</i> function can simply return control.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CL_ADD_PARTY_COMPLETE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param Status [in]

Specifies final status of the client-initiated add-party operation, which can be one of the
     following:
     





#### NDIS_STATUS_SUCCESS

The given party was added on the client's active multipoint VC.



#### NDIS_STATUS_RESOURCES

NDIS could not allocate sufficient resources to track the new party.



#### NDIS_STATUS_FAILURE

The client passed an invalid 
       <i>NdisVcHandle</i> to 
       <b>NdisClAddParty</b>.



#### NDIS_STATUS_XXX

The call manager's 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cm_add_party">ProtocolCmAddParty</a> function
       returned a CM-determined value to indicate why it could not add the party to the VC.


### -param ProtocolPartyContext [in]

Specifies the client-supplied handle originally passed to 
     <b>NdisClAddParty</b>.


### -param NdisPartyHandle [in]

If 
     <i>Status</i> is NDIS_STATUS_SUCCESS, this NDIS-supplied handle represents the association between the
     call manager and client regarding this party. Otherwise, the attempt to add a party failed and the
     client should consider this parameter an invalid handle.


### -param CallParameters [in]

Pointer to a structure of type 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a>, originally set up by
     the client for its call to 
     <b>NdisClAddParty</b> but possibly modified subsequently by the call manager.


## -returns



None




## -remarks



A call to 
    <i>ProtocolClAddPartyComplete</i> indicates completion of the asynchronous operation initiated when the
    client called 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscladdparty">NdisClAddParty</a>. If the input 
    <i>Status</i> is set to anything other than NDIS_STATUS_SUCCESS, 
    <i>ProtocolClAddPartyComplete</i> can release or reuse the client-allocated buffers at 
    <i>ProtocolPartyContext</i> and at 
    <i>CallParameters</i> .

If the attempt to add a party succeeded, 
    <i>ProtocolClAddPartyComplete</i> should save the input 
    <i>NdisPartyHandle</i> for subsequent calls to NDIS library functions concerning this party in the
    client's 
    <i>ProtocolPartyContext</i> area. For example, the client must pass this handle in a subsequent call to 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscldropparty">NdisClDropParty</a> eventually unless the
    remote party that it represents closes its connection first.

The structure at 
    <i>CallParameters</i> originally was allocated and initialized by the client, which passed this pointer to    
    <b>NdisClAddParty</b>. However, the call manager might have modified the client-supplied values to
    reflect the results of the CM's negotiation with the network or with a signaling peer while processing
    the client's add-party request. To determine whether the call manager made any modifications, 
    <i>ProtocolClAddPartyComplete</i> can check the 
    <b>Flags</b> member of this structure for whether CALL_PARAMETERS_CHANGED is set. If so, 
    <i>ProtocolClAddPartyComplete</i> must update the per-party state that the client maintains for this call
    at 
    <i>ProtocolPartyContext</i> unless it finds the CM's modifications unacceptable. The particular signaling
    protocol determines what the client can do in this case. Usually, a client calls 
    <b>NdisClDropParty</b> if it finds the CM-modified call parameters unacceptable.

Depending on the signaling protocol of the call manager, the traffic parameters at 
    <i>CallParameters</i> can be identical for all parties on any particular multipoint connection. That is,
    as the client of such a call manager adds parties on a multipoint connection that the client originally
    set up with 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisclmakecall">NdisClMakeCall</a>, it can supply only the
    target address of each party and leave the traffic parameters as originally set up for the multipoint VC
    each time it calls 
    <b>NdisClAddParty</b>.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolClAddPartyComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolClAddPartyComplete</i> function that is named "MyClAddPartyComplete", use the <b>PROTOCOL_CL_ADD_PARTY_COMPLETE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CL_ADD_PARTY_COMPLETE MyClAddPartyComplete;</pre>
</td>
</tr>
</table></span></div>
Then, implement your function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyClAddPartyComplete(
    NDIS_STATUS  Status,
    NDIS_HANDLE  ProtocolPartyContext,
    NDIS_HANDLE  NdisPartyHandle,
    PCO_CALL_PARAMETERS  CallParameters
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CL_ADD_PARTY_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_ADD_PARTY_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscladdparty">NdisClAddParty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscldropparty">NdisClDropParty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisclmakecall">NdisClMakeCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscmaddpartycomplete">NdisCmAddPartyComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismcmaddpartycomplete">NdisMCmAddPartyComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cl_incoming_drop_party">ProtocolClIncomingDropParty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cm_add_party">ProtocolCmAddParty</a>
 

 

