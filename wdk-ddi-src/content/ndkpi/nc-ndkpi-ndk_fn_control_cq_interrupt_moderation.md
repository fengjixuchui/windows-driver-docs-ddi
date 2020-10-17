---
UID: NC:ndkpi.NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION
title: NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION (ndkpi.h)
description: The NdkControlCqInterruptModeration (NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION) function controls interrupt moderation on an NDK completion queue (CQ).
old-location: netvista\ndk_fn_control_cq_interrupt_moderation.htm
tech.root: netvista
ms.assetid: 44EB6C92-1ADA-4675-9E19-BAB79097FF5B
ms.date: 05/02/2018
keywords: ["NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION callback function"]
ms.keywords: NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION, NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION callback, NdkControlCqInterruptModeration, NdkControlCqInterruptModeration callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkControlCqInterruptModeration, netvista.ndk_fn_control_cq_interrupt_moderation
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION
 - ndkpi/NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ndkpi.h
api_name:
 - NdkControlCqInterruptModeration
---

# NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION callback function


## -description

The <i>NdkControlCqInterruptModeration</i> (<i>NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION</i>) function controls interrupt moderation on an NDK completion queue (CQ).

For more information about interrupt moderation, see <a href="/windows-hardware/drivers/network/interrupt-moderation">Interrupt Moderation</a>.

## -parameters

### -param pNdkCq 

[in]
A pointer to an NDK completion queue object (<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_cq">NDK_CQ</a>).

### -param ModerationInterval 

[in]

The maximum number of microseconds that a provider can defer interrupting the host CPU after a completion placed into the CQ satisfies an arm request. If <i>ModerationInterval</i> is zero, the provider performs no interrupt moderation  on the CQ regardless of the value of the <i>ModerationCount</i> parameter. If <i>ModerationInterval</i> is MAXULONG, the  <i>ModerationCount</i> controls the interrupt moderation on the CQ. If <i>ModerationInterval</i> is larger than the maximum moderation interval that the adapter supports or if the adapter’s timer granularity is larger, the provider can round down the interval value.

### -param ModerationCount 

[in]

The maximum number of completions that a provider can accumulate in the CQ before interrupting the host CPU to satisfy a CQ arm request. If  <i>ModerationInterval</i> is zero  or one,  the provider performs no interrupt moderation on the CQ regardless of the value of the <i>ModerationInterval</i> parameter. If <i>ModerationCount</i> is MAXULONG or larger than the depth of the CQ,   <i>ModerationInterval</i> controls the interrupt moderation on the CQ.

## -returns

The 
     <i>NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION</i> function returns one of the following NTSTATUS codes.

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
The operation completed successfully.

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

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The NDK 
provider does not support CQ interrupt moderation control with <a href="/windows-hardware/drivers/ddi/ndkpi/nc-ndkpi-ndk_fn_control_cq_interrupt_moderation">NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION</a>. A provider that sets the NDK_ADAPTER_FLAG_CQ_INTERRUPT_MODERATION_SUPPORT flag in the <a href="/windows/win32/api/ndkinfo/ns-ndkinfo-ndk_adapter_info">NDK_ADAPTER_INFO</a> structure's <b>AdapterFlags</b> member must not return this status code.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_MIX</b></dt>
</dl>
</td>
<td width="60%">
The NDK 
consumer provided a MAXULONG for <i>ModerationInterval</i> and MAXULONG or a value larger than the  number of completion entries that the CQ can hold for <i>ModerationCount</i> at the same time.


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

NDK consumers must not call <i>NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION</i> unless the provider sets the NDK_ADAPTER_FLAG_CQ_INTERRUPT_MODERATION_SUPPORTED  flag in the <a href="/windows/win32/api/ndkinfo/ns-ndkinfo-ndk_adapter_info">NDK_ADAPTER_INFO</a> structure's <b>AdapterFlags</b> member. For a provider that sets the NDK_ADAPTER_FLAG_CQ_INTERRUPT_MODERATION_SUPPORTED flag, the NDK consumer can call this function at any point after a CQ is created. The default behavior for a CQ is no interrupt moderation. The NDK consumer must not call this function on the same CQ concurrently.


The NDK consumer must not specify a MAXULONG for <i>ModerationInterval</i> and MAXULONG or a value larger than the  number of completion entries that the CQ can hold  (<i>CqDepth</i>) for <i>ModerationCount</i> at the same time. Otherwise, the provider will return STATUS_INVALID_PARAMETER_MIX.


The NDK consumer can call <i>NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION</i> multiple times. A provider might not apply the settings before returning from this function.  However, the provider must not delay the application of the settings indefinitely. If the consumer issues another call to this function while the provider has not yet applied the settings from a previous invocation of the function, the provider must make the most recently provided settings effective as soon as possible. That is, either the provider must cancel the application of the previous settings and apply the new settings, or wait for the application of previous settings to complete and apply the new settings.

Providers that indicate support for interrupt moderation with the NDK_ADAPTER_FLAG_CQ_INTERRUPT_MODERATION_SUPPORTED flag must normally handle <i>NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION</i> successfully and return STATUS_SUCCESS.  However,  a provider can fail the request due to a resource shortage such as a memory allocation failure. In this case,  the provider must return STATUS_INSUFFICIENT_RESOURCES. Providers cannot return STATUS_PENDING from this function. Providers that do not indicate support for this function with the NDK_ADAPTER_FLAG_CQ_INTERRUPT_MODERATION_SUPPORTED flag must still implement this function. In this case,  this function  must return STATUS_NOT_SUPPORTED.

## -see-also

<a href="/windows/win32/api/ndkinfo/ns-ndkinfo-ndk_adapter_info">NDK_ADAPTER_INFO</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_cq">NDK_CQ</a>



<a href="/windows-hardware/drivers/ddi/ndkpi/ns-ndkpi-_ndk_cq_dispatch">NDK_CQ_DISPATCH</a>