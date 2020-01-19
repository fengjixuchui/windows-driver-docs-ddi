---
UID: NC:ndis.PROTOCOL_CO_AF_REGISTER_NOTIFY
title: PROTOCOL_CO_AF_REGISTER_NOTIFY (ndis.h)
description: The ProtocolCoAfRegisterNotify function is used by connection-oriented NDIS clients.
old-location: netvista\protocolcoafregisternotify.htm
tech.root: netvista
ms.assetid: 272d99da-ef08-4ebd-90e7-74e99410b3f5
ms.date: 05/02/2018
ms.keywords: PROTOCOL_CO_AF_REGISTER_NOTIFY, PROTOCOL_CO_AF_REGISTER_NOTIFY callback, ProtocolCoAfRegisterNotify, ProtocolCoAfRegisterNotify callback function [Network Drivers Starting with Windows Vista], condis_protocol_ref_aa4ed4ae-7fa9-4f92-9103-824fbe719739.xml, ndis/ProtocolCoAfRegisterNotify, netvista.protocolcoafregisternotify
ms.topic: callback
f1_keywords:
 - "ndis/ProtocolCoAfRegisterNotify"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolCoAfRegisterNotify   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolCoAfRegisterNotify   (NDIS 5.1)) in Windows XP.
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- ProtocolCoAfRegisterNotify
product:
- Windows
targetos: Windows
req.typenames: 
---

# PROTOCOL_CO_AF_REGISTER_NOTIFY callback function


## -description


The 
  <i>ProtocolCoAfRegisterNotify</i> function is used by connection-oriented NDIS clients. All
  connection-oriented NDIS clients must have fully functional 
  <i>ProtocolCoAfRegisterNotify</i> functions. Stand-alone connection-oriented call managers have registered 
  <i>ProtocolCoAfRegisterNotify</i> functions that simply return control.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CO_AF_REGISTER_NOTIFY</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters




### -param ProtocolBindingContext [in]

Specifies the handle to the client-allocated context area in which the client protocol maintains
     per-binding run-time state. The client's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a> function
     supplied this handle when it called 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>.


### -param AddressFamily [in]

Pointer to a buffer describing the signaling-protocol support provided by a call manager that just
     registered these services with NDIS by calling 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmregisteraddressfamilyex">
     NdisCmRegisterAddressFamilyEx</a> or 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmregisteraddressfamilyex">
     NdisMCmRegisterAddressFamilyEx</a>.


## -returns



None




## -remarks



A call to 
    <i>ProtocolCoAfRegisterNotify</i> advertises a particular call manager's or MCM driver's call-management
    services on an underlying connection-oriented NIC to which the client is bound.

<i>ProtocolCoAfRegisterNotify</i> examines the data at 
    <i>AddressFamily</i> to determine whether the client can use the services of this particular call manager.
    Whether the client can make modifications in the (M)CM-supplied data at 
    <i>AddressFamily</i> depends on the particular signaling-protocol support of the call manager.

If the client finds the offered call-management services unacceptable, 
    <i>ProtocolCoAfRegisterNotify</i> returns control, and NDIS might call 
    <i>ProtocolCoAfRegisterNotify</i> again with the same 
    <i>ProtocolBindingContext</i> handle and an AF specification supplied by this or another call manager also
    bound to the same underlying miniport driver. Otherwise, 
    <i>ProtocolAfRegisterNotify</i> allocates a per-AF context area for the client and calls 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclopenaddressfamilyex">NdisClOpenAddressFamilyEx</a> with
    the 
    <i>AddressFamily</i> pointer. If this call succeeds, the client has registered its 
    <i>ProtocolClXxx</i> functions with NDIS for subsequent connection-oriented operations using this call manager's
    services.

For example, 
    <i>ProtocolCoAfRegisterNotify</i> or 
    <i>ProtocolClOpenAfCompleteEx</i> might call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinitializenpagedlookasidelist">
    NdisInitializeNPagedLookasideList</a> one or more times in preparation for dynamic allocations and
    releases of per-SAP, per-VC, and/or per-party context areas that the client will need subsequently.

If it accepts incoming calls, a client's 
    <i>ProtocolCoAfRegisterNotify</i> or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_open_af_complete_ex">
    ProtocolClOpenAfCompleteEx</a> function usually registers one or more SAPs with the call manager. After
    opening that call manager's AF, the client might proceed to allocate a per-SAP state area and call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclregistersap">NdisClRegisterSap</a> one or more times with
    the 
    <i>NdisAfHandle</i> it obtained from 
    <b>NdisClOpenAddressFamilyEx</b>. If it makes outgoing calls, the client might proceed to allocated a
    per-VC state area and create a VC with 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscocreatevc">NdisCoCreateVc</a> in anticipation of an
    incoming request from one of its own clients to make an outgoing call to a remote node.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolCoAfRegisterNotify</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCoAfRegisterNotify</i> function that is named "MyCoAfRegisterNotify", use the <b>PROTOCOL_CO_AF_REGISTER_NOTIFY</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CO_AF_REGISTER_NOTIFY MyCoAfRegisterNotify;</pre>
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
 MyCoAfRegisterNotify(
    NDIS_HANDLE  ProtocolBindingContext,
    PCO_ADDRESS_FAMILY  AddressFamily
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CO_AF_REGISTER_NOTIFY</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CO_AF_REGISTER_NOTIFY</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545368(v=vs.85)">CO_ADDRESS_FAMILY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclopenaddressfamilyex">NdisClOpenAddressFamilyEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclregistersap">NdisClRegisterSap</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmregisteraddressfamilyex">
   NdisCmRegisterAddressFamilyEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscocreatevc">NdisCoCreateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisinitializenpagedlookasidelist">
   NdisInitializeNPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmregisteraddressfamilyex">
   NdisMCmRegisterAddressFamilyEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_open_af_complete_ex">ProtocolClOpenAfCompleteEx</a>
 

 

