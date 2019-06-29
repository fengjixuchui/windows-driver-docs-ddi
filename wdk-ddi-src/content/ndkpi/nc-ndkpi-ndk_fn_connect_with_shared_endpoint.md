---
UID: NC:ndkpi.NDK_FN_CONNECT_WITH_SHARED_ENDPOINT
title: NDK_FN_CONNECT_WITH_SHARED_ENDPOINT (ndkpi.h)
description: The NdkConnectWithSharedEndpoint (NDK_FN_CONNECT_WITH_SHARED_ENDPOINT) function initiates an NDK connect request from a shared local address to a remote address.
old-location: netvista\ndk_fn_connect_with_shared_endpoint.htm
tech.root: netvista
ms.assetid: E97C0B87-C031-4C91-8FFF-86B5E8324FB8
ms.date: 05/02/2018
ms.keywords: NDK_FN_CONNECT_WITH_SHARED_ENDPOINT, NDK_FN_CONNECT_WITH_SHARED_ENDPOINT callback, NdkConnectWithSharedEndpoint, NdkConnectWithSharedEndpoint callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkConnectWithSharedEndpoint, netvista.ndk_fn_connect_with_shared_endpoint
ms.topic: callback
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ndkpi.h
api_name:
- NdkConnectWithSharedEndpoint
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDK_FN_CONNECT_WITH_SHARED_ENDPOINT callback function


## -description


The <i>NdkConnectWithSharedEndpoint</i> (<i>NDK_FN_CONNECT_WITH_SHARED_ENDPOINT</i>) function initiates an NDK connect request from a shared local address to a remote address. 


## -parameters




### -param *pNdkConnector [in]

A pointer to an NDK connector object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_connector">NDK_CONNECTOR</a>).


### -param *pNdkQp [in]

A pointer to an NDK queue pair (QP) object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_qp">NDK_QP</a>) to be associated with the connection.


### -param *pNdkSharedEndpoint [in]

A pointer to an NDK shared endpoint object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_shared_endpoint">NDK_SHARED_ENDPOINT</a>) that determines the local address for the connection.


### -param PSOCKADDR

A destination address.  For AF_INET or AF_INET6 <i>pDestAddress</i>  is the destination IP address and the destination ND port.

### -param DestAddressLength [in]

The size, in bytes,  of destination address data at the <i>pDestAddress.</i> parameter.


### -param InboundReadLimit [in]

The consumer-supplied maximum number of incoming in-progress read operations to allow on the QP. If the underlying provider has a lower <b>MaxInboundReadLimit</b> value in the <a href="https://docs.microsoft.com/windows/desktop/api/ndkinfo/ns-ndkinfo-_ndk_adapter_info">NDK_ADAPTER_INFO</a> structure, then the provider will cap the consumer-supplied value to the provider maximum. If the peer has a lower <i>OutboundReadLimit</i> value, then the provider will use that value as the effective <i>InboundReadLimit</i>. The consumer can retrieve the effective <i>InboundReadLimit</i> by calling the <i>NdkGetConnectionData</i> function (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_get_connection_data">NDK_FN_GET_CONNECTION_DATA</a>).


### -param OutboundReadLimit [in]

The consumer-supplied maximum number of outgoing in-progress read operations to allow on the QP. If the underlying provider has a lower <b>MaxOutboundReadLimit</b> value  in the <a href="https://docs.microsoft.com/windows/desktop/api/ndkinfo/ns-ndkinfo-_ndk_adapter_info">NDK_ADAPTER_INFO</a> structure, then the provider will cap the consumer supplied value to the provider maximum. If the peer has a lower <i>InboundReadLimit</i>, then the provider will use that value as the effective <i>OutboundReadLimit</i>. The     consumer can retrieve the effective <i>OutboundReadLimit</i> by calling the <i>NdkGetConnectionData</i> function (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_get_connection_data">NDK_FN_GET_CONNECTION_DATA</a>).


### -param PVOID

A pointer to private data that is sent with the connect request.

### -param PrivateDataLength [in]

The length, in bytes, of the private data that is provided in the <i>pPrivateData</i> parameter.


### -param RequestCompletion [in]

A pointer to a request completion callback routine <i>NdkRequestCompletion</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_request_completion">NDK_FN_REQUEST_COMPLETION</a>).


### -param RequestContext [in, optional]

A context value to pass to the <i>Context</i> parameter of the  callback function that is specified in the <i>RequestCompletion</i> parameter.

## -returns



The 
     <i>NdkConnectWithSharedEndpoint</i> function returns one of the following NTSTATUS codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The connect request was completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
 The operation is pending and will be completed later. The driver will call the specified <i>RequestCompletion</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_request_completion">NDK_FN_REQUEST_COMPLETION</a>) function to complete the pending operation.
 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The  request failed due to insufficient resources. 

<div class="alert"><b>Important</b>  The request can fail inline as well as asynchronously with this status code.</div>
<div> </div>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NETWORK_UNREACHABLE</b></dt>
</dl>
</td>
<td width="60%">
The request failed because the remote network was not reachable. The connection attempt may be retried. 

<div class="alert"><b>Important</b>  The request can fail inline as well as asynchronously with this status code.</div>
<div> </div>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_HOST_UNREACHABLE</b></dt>
</dl>
</td>
<td width="60%">
The request failed because the remote system was not reachable. The connection attempt may be retried. 

<div class="alert"><b>Important</b>  The request can fail inline as well as asynchronously with this status code.</div>
<div> </div>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CONNECTION_REFUSED</b></dt>
</dl>
</td>
<td width="60%">
The request failed because the remote system refused the connection request. This can be due to lack of listener, backlog limits, or the peer actively rejecting the connection request. The connection attempt may be retried. 

<div class="alert"><b>Important</b>  The request can fail inline as well as asynchronously with this status code.</div>
<div> </div>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_IO_TIMEOUT</b></dt>
</dl>
</td>
<td width="60%">
The request failed because the connection request timed out. The connection attempt may be retried. Timeout values are selected by Network Direct providers to match their respective network characteristics.

<div class="alert"><b>Important</b>  The request can fail inline as well as asynchronously with this status code.</div>
<div> </div>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ADDRESS_ALREADY_EXISTS</b></dt>
</dl>
</td>
<td width="60%">
The request failed because a connection with the combination of local address, local port, remote address, and remote port already exists. 

<div class="alert"><b>Important</b>  The request can fail inline as well as asynchronously with this status code.</div>
<div> </div>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred. 

</td>
</tr>
</table>
 




## -remarks



<i>NdkConnectWithSharedEndpoint</i> initiates a connect request from a shared local address to a specific remote address. <i>NdkConnectWithSharedEndpoint</i> allows an NDK consumer to use the same local address (for example, 10.1.1.1:9999) for many outgoing connections when the destination addresses for the connections are different.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndkpi-object-lifetime-requirements">NDKPI Object Lifetime Requirements</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ndkinfo/ns-ndkinfo-_ndk_adapter_info">NDK_ADAPTER_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_connector">NDK_CONNECTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_connector_dispatch">NDK_CONNECTOR_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_get_connection_data">NDK_FN_GET_CONNECTION_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_request_completion">NDK_FN_REQUEST_COMPLETION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_qp">NDK_QP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_shared_endpoint">NDK_SHARED_ENDPOINT</a>
 

 

