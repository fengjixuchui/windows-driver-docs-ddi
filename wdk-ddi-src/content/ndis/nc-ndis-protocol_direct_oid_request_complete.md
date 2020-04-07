---
UID: NC:ndis.PROTOCOL_DIRECT_OID_REQUEST_COMPLETE
title: PROTOCOL_DIRECT_OID_REQUEST_COMPLETE (ndis.h)
description: The ProtocolDirectOidRequestComplete function completes the processing of a protocol driver-initiated direct OID request for which the NdisDirectOidRequest function returned NDIS_STATUS_PENDING.Note  You must declare the function by using the PROTOCOL_DIRECT_OID_REQUEST_COMPLETE type. For more information, see the following Examples section.
old-location: netvista\protocoldirectoidrequestcomplete.htm
tech.root: netvista
ms.assetid: 6b23bbba-1b18-4da7-a45c-68df7c960aad
ms.date: 05/02/2018
keywords: ["PROTOCOL_DIRECT_OID_REQUEST_COMPLETE callback function"]
ms.keywords: PROTOCOL_DIRECT_OID_REQUEST_COMPLETE, PROTOCOL_DIRECT_OID_REQUEST_COMPLETE callback, ProtocolDirectOidRequestComplete, ProtocolDirectOidRequestComplete callback function [Network Drivers Starting with Windows Vista], ndis/ProtocolDirectOidRequestComplete, ndis_request_direct_ref_d190a2bd-5db1-481e-aaee-deffd87c8968.xml, netvista.protocoldirectoidrequestcomplete
f1_keywords:
 - "ndis/ProtocolDirectOidRequestComplete"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- ProtocolDirectOidRequestComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# PROTOCOL_DIRECT_OID_REQUEST_COMPLETE callback function


## -description


The 
  <i>ProtocolDirectOidRequestComplete</i> function completes the processing of a protocol
  driver-initiated direct OID request for which the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisdirectoidrequest">NdisDirectOidRequest</a> function returned
  NDIS_STATUS_PENDING.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_DIRECT_OID_REQUEST_COMPLETE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param ProtocolBindingContext [in]

A handle to a protocol driver-allocated context area in which the protocol driver maintains
     per-binding run-time state. The driver supplied this handle when it called the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function.


### -param OidRequest [in]

A pointer to the protocol driver-supplied 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure that was
     previously passed to the 
     <b>NdisDirectOidRequest</b> function.


### -param Status [in]

The final status of the request. The underlying driver or NDIS determines this final status. This
     parameter determines what 
     <i>ProtocolDirectOidRequestComplete</i> does with the information at 
     <i>OidRequest</i>.


## -remarks



<i>ProtocolDirectOidRequestComplete</i> is an optional function. If a protocol driver
    does not use direct OID requests, it can set the entry point for this function to <b>NULL</b> when it calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterprotocoldriver">
    NdisRegisterProtocolDriver</a> function.

<i>ProtocolDirectOidRequestComplete</i> uses the input value of the 
    <i>Status</i> parameter as follows:

<ul>
<li>
If 
      <i>Status</i> is NDIS_STATUS_SUCCESS, the 
      <b>BytesRead</b> or 
      <b>BytesWritten</b> member of the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure has been set
      by NDIS or the underlying driver. These values specify how much protocol driver-supplied information
      was transferred from the buffer at 
      <b>InformationBuffer</b> to the NIC in a set operation or how much information
      was returned at 
      <b>InformationBuffer</b> in response to a query operation.

If the protocol driver made a query, 
      <i>ProtocolDirectOidRequestComplete</i> can use the data that is returned at 
      <b>InformationBuffer</b> in any way that the protocol driver determines,
      depending on the value of the 
      <b>Oid</b> member.

For example, if the protocol driver originally initiated an 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-maximum-send-packets">
      OID_GEN_MAXIMUM_SEND_PACKETS</a> query, 
      <i>ProtocolDirectOidRequestComplete</i> might set up state variables in the 
      <i>ProtocolBindingContext</i> area to throttle the number of outstanding sends that
      the driver will set up for subsequent calls to the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissendnetbufferlists">
      NdisSendNetBufferLists</a> function.

</li>
<li>
If 
      <i>Status</i> is NDIS_STATUS_INVALID_LENGTH or NDIS_STATUS_BUFFER_TOO_SHORT, the 
      <b>BytesNeeded</b> member specifies the OID-specific value of the 
      <b>InformationBufferLength</b> member that is required to carry out the
      requested operation.

In these circumstances, 
      <i>ProtocolDirectOidRequestComplete</i> can allocate sufficient buffer space for the
      request, set up another NDIS_OID_REQUEST structure with the required 
      <b>InformationBufferLength</b> value and same 
      <b>Oid</b> value, and retry the call to the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisdirectoidrequest">NdisDirectOidRequest</a> function.

<i>ProtocolDirectOidRequestComplete</i> can retry requests for certain other
      NDIS_STATUS_
      <i>Xxx</i> arguments, as well, as described in 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisdirectoidrequest">NdisDirectOidRequest</a>.

</li>
<li>
If 
      <i>Status</i> is an NDIS_STATUS_
      <i>Xxx</i> value that is an unrecoverable error, 
      <i>ProtocolDirectOidRequestComplete</i> should release the memory that is allocated
      for the NDIS_OID_REQUEST structure and determine whether the driver should close the binding or adjust
      its binding-specific state information to handle continued network I/O operations on the binding.

</li>
</ul>
<i>ProtocolDirectOidRequestComplete</i> can be called before the protocol driver has
    had time to inspect the status code that 
    <b>NdisDirectOidRequest</b> returns at 
    <i>Status</i>.

NDIS calls 
    <i>ProtocolDirectOidRequestComplete</i> at IRQL <= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolDirectOidRequestComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolDirectOidRequestComplete</i> function that is named "MyDirectOidRequestComplete", use the <b>PROTOCOL_DIRECT_OID_REQUEST_COMPLETE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_DIRECT_OID_REQUEST_COMPLETE MyDirectOidRequestComplete;</pre>
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
 MyDirectOidRequestComplete(
    NDIS_HANDLE  ProtocolBindingContext,
    PNDIS_OID_REQUEST  OidRequest,
    NDIS_STATUS  Status
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_DIRECT_OID_REQUEST_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_DIRECT_OID_REQUEST_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisdirectoidrequest">NdisDirectOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismdirectoidrequestcomplete">
   NdisMDirectOidRequestComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterprotocoldriver">NdisRegisterProtocolDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-maximum-send-packets">OID_GEN_MAXIMUM_SEND_PACKETS</a>
 

 

