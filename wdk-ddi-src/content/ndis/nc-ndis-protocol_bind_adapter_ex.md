---
UID: NC:ndis.PROTOCOL_BIND_ADAPTER_EX
title: PROTOCOL_BIND_ADAPTER_EX (ndis.h)
description: NDIS calls a protocol driver's ProtocolBindAdapterEx function to request the driver to bind to a miniport adapter.Note  You must declare the function by using the PROTOCOL_BIND_ADAPTER_EX type.
old-location: netvista\protocolbindadapterex.htm
tech.root: netvista
ms.assetid: 1958722e-012e-4110-a82c-751744bcf9b5
ms.date: 05/02/2018
ms.keywords: PROTOCOL_BIND_ADAPTER_EX, PROTOCOL_BIND_ADAPTER_EX callback, ProtocolBindAdapterEx, ProtocolBindAdapterEx callback function [Network Drivers Starting with Windows Vista], ndis/ProtocolBindAdapterEx, netvista.protocolbindadapterex, protocol_functions_ref_82268bd4-3e45-48ba-8b80-df47fbde11e1.xml
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
- ProtocolBindAdapterEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# PROTOCOL_BIND_ADAPTER_EX callback function


## -description


NDIS calls a protocol driver's 
  <i>ProtocolBindAdapterEx</i> function to request the driver to bind to a miniport
  adapter.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_BIND_ADAPTER_EX</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param ProtocolDriverContext [in]

A handle to a driver-allocated context area where the driver maintains state and configuration
     information. The protocol driver passed this context area to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisregisterprotocoldriver">
     NdisRegisterProtocolDriver</a> function.


### -param BindContext [in]

The handle that identifies the NDIS context area for this bind operation.


### -param BindParameters [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a> structure that
     NDIS created.


## -returns



<i>ProtocolBindAdapterEx</i> returns one of the following status values:

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
<i>ProtocolBindAdapterEx</i> successfully completed the binding to the underlying
       miniport adapter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
<i>ProtocolBindAdapterEx</i> did not complete the bind operation and the operation
       will be completed asynchronously. The protocol driver must call the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscompletebindadapterex">
       NdisCompleteBindAdapterEx</a> function when the operation is complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<i>ProtocolBindAdapterEx</i> could not allocate the resources that the driver
       requires to carry out network I/O operations.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_XXX or NTSTATUS_XXX</b></dt>
</dl>
</td>
<td width="60%">
The protocol driver's attempt to set up a binding failed. Usually, such an error status is
       propagated from an 
       <b>Ndis<i>Xxx</i></b> function or a kernel-mode support routine.

</td>
</tr>
</table>
 




## -remarks



<i>ProtocolBindAdapterEx</i> is a required function. NDIS calls 
    <i>ProtocolBindAdapterEx</i> to perform binding operations whenever an underlying
    miniport adapter, to which the protocol driver can bind, becomes available.

<i>ProtocolBindAdapterEx</i> allocates sufficient memory to maintain the binding
    context information and calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function to bind
    itself to the underlying miniport adapter. 
    <i>ProtocolBindAdapterEx</i> passes a pointer to the binding context information at
    the 
    <i>ProtocolBindingContext</i> parameter of 
    <b>NdisOpenAdapterEx</b>. 
    <i>ProtocolBindAdapterEx</i> passes the value at the 
    <b>AdapterName</b> member from its 
    <i>BindParameters</i> parameter as the 
    <b>AdapterName</b> member of the 
    <i>OpenParameters</i> parameter of 
    <b>NdisOpenAdapterEx</b><i>.</i>

Before the driver calls 
    <b>NdisOpenAdapterEx</b>, the driver can pass the pointer at 
    <i>BindParameters</i> to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndisopenconfigurationex">NdisOpenConfigurationEx</a> function
    to read the configuration parameters that are associated with a miniport adapter.

After opening the miniport adapter successfully, the driver can pass the handle from 
    <i>NdisHandle</i> parameter of 
    <b>NdisOpenAdapterEx</b> to 
    <b>NdisOpenConfigurationEx</b> to obtain a handle to the registry location where the configuration
    parameters for a protocol binding are stored.

<i>ProtocolBindAdapterEx</i> passes 
    <b>NdisOpenAdapterEx</b> a pointer to an array of medium type values that lists the types of media that
    the protocol driver can support. This list is a subset of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ne-ntddndis-_ndis_medium">NDIS_MEDIUM</a> types. NDIS indicates the selected
    medium type at the 
    <b>SelectedMediumIndex</b> parameter of the structure at 
    <i>OpenParameters</i>.

If 
    <b>NdisOpenAdapterEx</b> returns an error status, 
    <i>ProtocolBindAdapterEx</i> returns that error status, releases any per-binding
    resources that the protocol driver allocated, and returns control immediately.

If 
    <b>NdisOpenAdapterEx</b> returns NDIS_STATUS_SUCCESS, 
    <i>ProtocolBindAdapterEx</i> can allocate the remaining resources that the protocol
    driver needs to carry out network I/O on the binding. The driver can also configure any binding-specific
    context information that the driver uses to track network I/O operations.

If 
    <b>NdisOpenAdapterEx</b> returns NDIS_STATUS_PENDING, NDIS calls the protocol driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_open_adapter_complete_ex">
    ProtocolOpenAdapterCompleteEx</a> function after the open operation is complete. 
    <i>ProtocolOpenAdapterCompleteEx</i> can complete the binding operations. 
    <i>ProtocolBindAdapterEx</i> can store the 
    <i>BindContext</i> handle in the binding context area. NDIS passes 
    <i>ProtocolBindingContext</i> as an input parameter to the driver's 
    <i>ProtocolOpenAdapterCompleteEx</i> function.

If 
    <b>NdisOpenAdapterEx</b> returns NDIS_STATUS_PENDING, NDIS sets the 
    <b>SelectedMediumIndex</b> member of the structure at the 
    <i>OpenParameters</i> parameter and the value of the 
    <i>NdisBindingHandle</i> parameter after 
    <b>NdisOpenAdapterEx</b> returns. NDIS sets these values before calling 
    <i>ProtocolOpenAdapterCompleteEx</i>. Therefore, the protocol driver must store the
    open parameters structure, and the protocol binding handle in the context area at 
    <i>ProtocolBindingContext</i>(or any location that is valid until NDIS calls 
    <i>ProtocolOpenAdapterCompleteEx</i>).

A protocol driver cannot make OID requests on a binding until the open operation is complete. Because
    the binding is in the paused state after the open operation is complete, the protocol driver cannot make
    send requests until after NDIS restarts the binding.

After the open operation is complete, 
    <i>ProtocolBindAdapterEx</i> can return NDIS_STATUS_SUCCESS to complete the binding
    operation. 
    <i>ProtocolBindAdapterEx</i> can return NDIS_STATUS_PENDING to defer the completion of
    the binding operations to a later time. If 
    <i>ProtocolBindAdapterEx</i> returns NDIS_STATUS_PENDING, the driver must call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscompletebindadapterex">
    NdisCompleteBindAdapterEx</a> function after the binding operation is complete.

Protocol drivers should use the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a> structure to
    determine the underlying miniport adapter's capabilities. After the open operation is complete, depending
    on the underlying media, the protocol driver can call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisoidrequest">NdisOidRequest</a> function to query the
    underlying miniport driver (or NDIS) about additional miniport adapter capabilities. For more information
    about OID requests, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/protocol-driver-oid-requests">Protocol Driver OID Requests</a>.

NDIS can call a protocol driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_receive_net_buffer_lists">
    ProtocolReceiveNetBufferLists</a> function after the driver sets up a packet filter for the binding
    with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-current-packet-filter">
    OID_GEN_CURRENT_PACKET_FILTER</a> OID. If the underlying miniport adapter does not use a packet filter
    for incoming packets, receive indications are enabled after the open operation is complete. Protocol
    drivers can receive status indications at the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_status_ex">ProtocolStatusEx</a> function after the
    open operation is complete.

Every protocol driver should allocate sufficient 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure pools. The driver
    allocates network data descriptors from these pools for subsequent send operations.

If 
    <i>ProtocolBindAdapterEx</i> cannot allocate the resources it needs to carry out
    subsequent network I/O operations, it should free all resources it has already allocated, and return an
    appropriate error value.

NDIS calls a protocol driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_unbind_adapter_ex">
    ProtocolUnbindAdapterEx</a> function to request the driver to unbind from an underlying miniport
    adapter.

If the protocol driver successfully opens the miniport adapter but the bind operation fails (for
    example, as a result of a failed OID request), the driver must close the miniport adapter from within the
    context of 
    <i>ProtocolBindAdapterEx</i> or
    <i>ProtocolUnbindAdapterEx</i>. For example, the driver calls 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscloseadapterex">NdisCloseAdapterEx</a> from 
    <i>ProtocolBindAdapterEx</i> and waits for the close operation to complete before the
    driver returns from 
    <i>ProtocolBindAdapterEx</i>. As an alternative, if the driver returned
    NDIS_STATUS_PENDING from 
    <i>ProtocolBindAdapterEx</i>, the driver can call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisunbindadapter">NdisUnbindAdapter</a> function and call 
    <b>NdisCloseAdapterEx</b> in the 
    <i>ProtocolUnbindAdapterEx</i> function.

NDIS calls 
    <i>ProtocolBindAdapterEx</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolBindAdapterEx</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolBindAdapterEx</i> function that is named "MyBindAdapterEx", use the <b>PROTOCOL_BIND_ADAPTER_EX</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_BIND_ADAPTER_EX MyBindAdapterEx;</pre>
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
NDIS_STATUS
 MyBindAdapterEx(
    NDIS_HANDLE  ProtocolDriverContext,
    NDIS_HANDLE  BindContext,
    PNDIS_BIND_PARAMETERS  BindParameters
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_BIND_ADAPTER_EX</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_BIND_ADAPTER_EX</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ne-ntddndis-_ndis_medium">NDIS_MEDIUM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscloseadapterex">NdisCloseAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscompletebindadapterex">NdisCompleteBindAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisoidrequest">NdisOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndisopenconfigurationex">NdisOpenConfigurationEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisregisterprotocoldriver">NdisRegisterProtocolDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisunbindadapter">NdisUnbindAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-current-packet-filter">OID_GEN_CURRENT_PACKET_FILTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_open_adapter_complete_ex">
   ProtocolOpenAdapterCompleteEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_receive_net_buffer_lists">
   ProtocolReceiveNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_status_ex">ProtocolStatusEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_unbind_adapter_ex">ProtocolUnbindAdapterEx</a>
 

 

