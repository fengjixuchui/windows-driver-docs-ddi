---
UID: NF:netioddk.NmrWaitForClientDeregisterComplete
title: NmrWaitForClientDeregisterComplete function (netioddk.h)
description: The NmrWaitForClientDeregisterComplete function waits for the deregistration of a client module to complete.
old-location: netvista\nmrwaitforclientderegistercomplete.htm
tech.root: netvista
ms.assetid: aed0a69e-868c-4c7d-b601-003ff357da38
ms.date: 05/02/2018
keywords: ["NmrWaitForClientDeregisterComplete function"]
ms.keywords: NmrWaitForClientDeregisterComplete, NmrWaitForClientDeregisterComplete function [Network Drivers Starting with Windows Vista], netioddk/NmrWaitForClientDeregisterComplete, netvista.nmrwaitforclientderegistercomplete, nmrref_577f5784-0136-480d-bc2d-d9b8740bdf3a.xml
req.header: netioddk.h
req.include-header: Wsk.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
req.lib: Netio.lib
req.dll: 
req.irql: < DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NmrWaitForClientDeregisterComplete
 - netioddk/NmrWaitForClientDeregisterComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - netio.lib
 - netio.dll
api_name:
 - NmrWaitForClientDeregisterComplete
---

# NmrWaitForClientDeregisterComplete function


## -description

The 
  <b>NmrWaitForClientDeregisterComplete</b> function waits for the deregistration of a client module to
  complete.

## -parameters

### -param NmrClientHandle 

[in]
A handle used by the NMR to represent the registration of the client module. The NMR returns this
     handle to the client module when the client module calls the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nf-netioddk-nmrregisterclient">NmrRegisterClient</a> function.

## -returns

The 
     <b>NmrWaitForClientDeregisterComplete</b> function returns one of the following NTSTATUS codes:

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
The NMR completed deregistering the client module.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The client module called the 
       <b>NmrWaitForClientDeregisterComplete</b> function before calling the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nf-netioddk-nmrderegisterclient">NmrDeregisterClient</a> function, or
       the handle specified in the NmrClientHandle parameter is not a valid client handle.

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

A client module calls the 
    <b>NmrWaitForClientDeregisterComplete</b> function to wait for the deregistration of the client module to
    complete. A client module calls the 
    <b>NmrWaitForClientDeregisterComplete</b> function only after calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nf-netioddk-nmrderegisterclient">NmrDeregisterClient</a> function.

A client module typically calls the 
    <b>NmrWaitForClientDeregisterComplete</b> function from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_unload">Unload</a> function to wait until it is completely
    deregistered from the NMR before the client module is unloaded from the system. A client module must not
    return from a call to its 
    <b>Unload</b> function until after deregistration is
    complete.


<div class="alert"><b>Note</b>  If a client module uses the Windows Driver Framework, it will typically call the 
     <b>NmrWaitForClientDeregisterComplete</b> function from its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_unload">EvtDriverUnload</a> event callback function. In
     this situation, the client module must not return from a call to its 
     <i>EvtDriverUnload</i> function until after
     deregistration is complete.</div>
<div> </div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nf-netioddk-nmrderegisterclient">NmrDeregisterClient</a>

