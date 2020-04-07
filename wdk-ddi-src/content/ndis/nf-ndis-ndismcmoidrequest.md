---
UID: NF:ndis.NdisMCmOidRequest
title: NdisMCmOidRequest function (ndis.h)
description: The NdisMCmOidRequest function sends an OID request from a miniport call manager (MCM) driver to a CoNDIS client.
old-location: netvista\ndismcmoidrequest.htm
tech.root: netvista
ms.assetid: c5523dff-4957-4265-82ef-2fbc009e6bef
ms.date: 05/02/2018
keywords: ["NdisMCmOidRequest function"]
ms.keywords: NdisMCmOidRequest, NdisMCmOidRequest function [Network Drivers Starting with Windows Vista], condis_request_ref_951cd477-8d0a-4882-921d-f394ac04f9cc.xml, ndis/NdisMCmOidRequest, netvista.ndismcmoidrequest
f1_keywords:
 - "ndis/NdisMCmOidRequest"
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
- NdisMCmOidRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMCmOidRequest function


## -description


The
  <b>NdisMCmOidRequest</b> function sends an OID request from a miniport call manager (MCM) driver to a CoNDIS
  client.


## -parameters




### -param NdisAfHandle [in]

A handle that identifies the address family (AF), and implicitly the client, that the OID request
     is directed to. The MCM driver originally obtained this handle as an input parameter to its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_open_af">ProtocolCmOpenAf</a> function.


### -param NdisVcHandle [in, optional]

A handle that identifies the virtual connection (VC) that the caller is requesting or setting
     information for, if the request is VC-specific. Otherwise, if this request is not VC-specific, this
     parameter is <b>NULL</b>. For any VC-specific request, the caller originally obtained this handle either when
     it created the VC with the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmcreatevc">NdisMCmCreateVc</a> function, or as an input
     parameter to its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a> function.


### -param NdisPartyHandle [in, optional]

A handle that identifies the party on a multipoint VC that the caller is requesting or setting
     information for, if the request is party-specific. Otherwise, if this request is not party-specific,
     this parameter is <b>NULL</b>. For any party-specific request, the MCM driver originally obtained this handle
     as an input parameter to its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_add_party">ProtocolCmAddParty</a> function.


### -param NdisOidRequest

A pointer to a caller-allocated buffer that contains an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure.

## -returns



<b>NdisMCmOidRequest</b> returns one of the following values:

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
The request operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The request is being handled asynchronously, and NDIS will call the caller's 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_oid_request_complete">
       ProtocolCoOidRequestComplete</a> function when the request is completed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_OID</b></dt>
</dl>
</td>
<td width="60%">
The OID_<i>XXX</i> code that was specified in the 
       <b>Oid</b> member of the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure at the 
       <i>OidRequest</i> parameter is invalid or unsupported by the underlying driver.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_LENGTH or NDIS_STATUS_BUFFER_TOO_SHORT</b></dt>
</dl>
</td>
<td width="60%">
The value that was specified in the 
       <b>InformationBufferLength</b> member of the NDIS_OID_REQUEST structure at 
       <i>OidRequest</i> does not match the requirements for the given OID_<i>XXX</i> code. If the information buffer is too small, the 
       <b>BytesNeeded</b> member of NDIS_OID_REQUEST contains the correct value for 
       <b>InformationBufferLength</b>, when 
       <b>NdisMCmOidRequest</b> returns.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_DATA</b></dt>
</dl>
</td>
<td width="60%">
The data that was supplied at 
       <b>InformationBuffer</b> in the given 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure was invalid
       for the given OID_<i>XXX</i> code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED or NDIS_STATUS_NOT_RECOGNIZED</b></dt>
</dl>
</td>
<td width="60%">
The client driver does not support the requested operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The request could not be satisfied because of a resource shortage. Usually, this return value
       indicates that an attempt to allocate memory was unsuccessful, but it does not necessarily indicate
       that the same request, if submitted later, will fail for the same reason.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
This value typically is a nonspecific default that is returned when none of the more specific
       NDIS_STATUS_<i>XXX</i> status codes applies.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_REQUEST_ABORTED</b></dt>
</dl>
</td>
<td width="60%">
The target driver stopped processing the request.

</td>
</tr>
</table>
 




## -remarks



To initiate OID requests to CoNDIS clients, MCM drivers call the 
    <b>NdisMCmOidRequest</b> function. Before an MCM driver calls 
    <b>NdisMCmOidRequest</b>, the driver allocates memory for its request and initializes an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure. The MCM sets
    the 
    <b>Oid</b> member of the NDIS_OID_REQUEST structure with a CoNDIS OID code.

An MCM driver can call 
    <b>NdisMCmOidRequest</b> to communicate connection-oriented information, such as a change in addresses to
    the client that the 
    <i>NdisAfHandle</i> parameter identifies.

After the MCM calls 
    <b>NdisMCmOidRequest</b>, NDIS calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_oid_request">ProtocolCoOidRequest</a> function of
    the client.

If the MCM driver's request is VC-specific or party-specific, the MCM driver also passes a non-<b>NULL</b>
    value at the 
    <i>NdisVcHandle</i> or 
    <i>NdisPartyHandle</i> parameter, respectively.

If 
    <b>NdisMCmOidRequest</b> returns NDIS_STATUS_PENDING, the request is being handled asynchronously and NDIS
    will call the MCM's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_oid_request_complete">
    ProtocolCoOidRequestComplete</a> function when the request is completed. If 
    <b>NdisMCmOidRequest</b> returns any other status, the request is complete when 
    <b>NdisMCmOidRequest</b> returns and NDIS does not call 
    <i>ProtocolCoOidRequestComplete</i>.

For more information about the OIDs that are defined to use with 
    <b>NdisMCmOidRequest</b>, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">NDIS OIDs</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmcreatevc">NdisMCmCreateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_add_party">ProtocolCmAddParty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_open_af">ProtocolCmOpenAf</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_oid_request">ProtocolCoOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_oid_request_complete">
   ProtocolCoOidRequestComplete</a>
 

 

