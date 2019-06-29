---
UID: NC:ndkpi.NDK_FN_CREATE_MW
title: NDK_FN_CREATE_MW (ndkpi.h)
description: The NdkCreateMw (NDK_FN_CREATE_MW) function creates an NDK memory window (MW) object.
old-location: netvista\ndk_fn_create_mw.htm
tech.root: netvista
ms.assetid: BAE0DF74-19AB-4AE9-A28C-C1CC2F569D1F
ms.date: 05/02/2018
ms.keywords: NDK_FN_CREATE_MW, NDK_FN_CREATE_MW callback, NdkCreateMw, NdkCreateMw callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkCreateMw, netvista.ndk_fn_create_mw
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
- NdkCreateMw
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDK_FN_CREATE_MW callback function


## -description


The <i>NdkCreateMw</i> (<i>NDK_FN_CREATE_MW</i>) function creates an NDK memory window (MW) object.


## -parameters




### -param *pNdkPd [in]

A pointer to an NDK protection domain (PD) object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_pd">NDK_PD</a>).


### -param CreateCompletion [in]

A pointer to an <i>NdkCreateCompletion</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>) function that completes the creation of an NDK object.


### -param RequestContext [in, optional]

A context value that the NDK provider passes back to the <i>NdkCreateCompletion</i> function that is specified in the <i>CreateCompletion</i> parameter.


#### -param **ppNdkMw

A pointer to a created MW object (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_mw">NDK_MW</a>) is returned in this location if  the request succeeds without returning STATUS_PENDING. If the request returns STATUS_PENDING then this parameter is ignored and the created object is returned  with the callback that is specified in the  <i>CreateCompletion</i> parameter.


## -returns



The 
     <i>NdkCreateMw</i> function returns one of the following NTSTATUS codes.

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
The MW object was created successfully and returned with the <i>*ppNdkMw</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
 The operation is pending and will be completed later. The provider will call the function specified in the <i>CreateCompletion</i> parameter(<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>) to complete the pending operation.
 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The request failed due to insufficient resources. 

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



The <i>NdkCreateMw</i> function creates an  NDK memory window (MW) object that can be used for bind requests. If the function returns STATUS_SUCCESS, the created object is returned in the <i>ppNdkMw</i> parameter. If <i>NdkCreateMw</i> returns STATUS_PENDING, the created object is returned by the <i>NdkCreateCompletion</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>) function that is specified in the <i>CreateCompletion</i> parameter.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndkpi-object-lifetime-requirements">NDKPI Object Lifetime Requirements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/nc-ndkpi-ndk_fn_create_completion">NDK_FN_CREATE_COMPLETION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_mw">NDK_MW</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndkpi/ns-ndkpi-_ndk_pd">NDK_PD</a>
 

 

