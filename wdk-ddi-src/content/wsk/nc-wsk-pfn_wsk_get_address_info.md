---
UID: NC:wsk.PFN_WSK_GET_ADDRESS_INFO
title: PFN_WSK_GET_ADDRESS_INFO (wsk.h)
description: The WskGetAddressInfo function performs protocol-independent translation from a host name to a transport address.
old-location: netvista\wskgetaddressinfo.htm
tech.root: netvista
ms.assetid: 688619b9-ab0b-4459-8f1b-74815043a190
ms.date: 05/02/2018
keywords: ["PFN_WSK_GET_ADDRESS_INFO callback function"]
ms.keywords: PFN_WSK_GET_ADDRESS_INFO, PFN_WSK_GET_ADDRESS_INFO callback, WskGetAddressInfo, WskGetAddressInfo callback function [Network Drivers Starting with Windows Vista], netvista.wskgetaddressinfo, wsk/WskGetAddressInfo, wskref_4b8f8dcc-eebb-4613-b130-3f7ae2921a8b.xml
f1_keywords:
 - "wsk/WskGetAddressInfo"
 - "WskGetAddressInfo"
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
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
- wsk.h
api_name:
- WskGetAddressInfo
targetos: Windows
req.typenames: 
---

# PFN_WSK_GET_ADDRESS_INFO callback function


## -description


The 
  <i>WskGetAddressInfo</i> function performs protocol-independent translation from a host name to a transport
  address.


## -parameters




### -param Client [in]

[in] A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wsk-client">WSK_CLIENT</a> structure that was returned through
     the 
     <i>WskProviderNpi</i> parameter of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nf-wsk-wskcaptureprovidernpi">
     WskCaptureProviderNPI</a> function.


### -param NodeName [in, optional]

[in] An optional pointer to a 
     <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains a
     Unicode string that represents a host (node) name or a numeric host address string. For the Internet
     protocol, the numeric host address string is a dotted-decimal IPv4 address or an IPv6 hexadecimal
     address.


### -param ServiceName [in, optional]

[in] An optional pointer to a 
     <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains a
     Unicode string that represents a service name or a port number.


### -param NameSpace [in, optional]

[in] An optional namespace identifier that specifies the namespace providers that are queried.
     Only namespace providers that support the specified namespace can be queried successfully.


### -param Provider [in, optional]

[in] An optional pointer to a GUID of a specific namespace provider to be queried.


### -param Hints [in, optional]

[in] An optional pointer to an <a href="https://docs.microsoft.com/windows/desktop/api/ws2def/ns-ws2def-addrinfoexw">ADDRINFOEXW</a> structure that provides hints about the type of socket
     that the caller supports.
     

The <a href="https://docs.microsoft.com/windows/desktop/api/ws2def/ns-ws2def-addrinfoexw">ADDRINFOEXW</a> structure is defined in the 
     Ws2def.h header. It is identical to the  
     <a href="https://docs.microsoft.com/windows/desktop/api/ws2def/ns-ws2def-addrinfoexw">addrinfoex</a> structure.

<div class="alert"><b>Important</b>  The 
     Ws2def.h header file is automatically included in 
     Wsk.h. Do not use 
     Ws2def.h directly.</div>
<div> </div>

### -param Result [out]

[out] A pointer to a caller-allocated buffer that receives a linked list of one or more
     <a href="https://docs.microsoft.com/windows/desktop/api/ws2def/ns-ws2def-addrinfoexw">ADDRINFOEXW</a> structures that represent response information about the host.
     

<div class="alert"><b>Note</b>  The caller must call the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_free_address_info">WskFreeAddressInfo</a> function to free
     this pointer.</div>
<div> </div>
The <a href="https://docs.microsoft.com/windows/desktop/api/ws2def/ns-ws2def-addrinfoexw">ADDRINFOEXW</a> structure is defined in the 
     Ws2def.h header. It is identical to the 
     <a href="https://docs.microsoft.com/windows/desktop/api/ws2def/ns-ws2def-addrinfoexw">addrinfoex</a> structure.

<div class="alert"><b>Important</b>  The 
     Ws2def.h header file is automatically included in 
     Wsk.h. Do not use 
     Ws2def.h directly.</div>
<div> </div>

### -param OwningProcess [in, optional]

[in] An optional pointer to the process from which the function retrieves the security context.
     This security context indicates the user account context in which the function processes the name
     resolution request.
     

If this parameter is <b>NULL</b>, the function processes the name resolution request in the context of a
     predefined local account with minimal privileges.

If this parameter is not <b>NULL</b> and an impersonation token is in effect for the calling thread, this
     function fails and returns STATUS_INVALID_PARAMETER.


### -param OwningThread [in, optional]

[in] An optional pointer to the thread from which the function retrieves the security context.
     This parameter can be non-<b>NULL</b> only if 
     <i>OwningProcess</i> is non-<b>NULL</b>. Otherwise, this function fails and returns STATUS_INVALID_PARAMETER.
     

If this parameter is not <b>NULL</b> and an impersonation token is in effect for the calling thread, this
     function fails and returns STATUS_INVALID_PARAMETER.


### -param Irp [in, out]

[in/out] A pointer to an I/O request packet (IRP) to use to complete the request asynchronously.
     Upon completion of the request, 
     <i>Irp</i> ->
     <b>Iostatus.Information</b> will hold the returned status code.


## -returns



<b>WskGetAddressInfo</b> returns one of the following NTSTATUS codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was specified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MATCH</b></dt>
</dl>
</td>
<td width="60%">
The host name cannot be resolved.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The function completed successfully. If the WSK application specified a pointer to an IRP in the
       
       <i>Irp</i> parameter, the IRP will be completed with a success status.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The WSK subsystem could not complete the function immediately. The WSK subsystem will complete
       the IRP after it has completed the control operation. The status of the control operation will be
       returned in the 
       <b>IoStatus.Status</b> field of the IRP.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred. The IRP will be completed with failure status.

</td>
</tr>
</table>
 




## -remarks



The process to which the 
    <i>OwningProcess</i> parameter points, or the thread to which the 
    <i>OwningThread</i> process points, indicates the security context for this function. The user account
    that is indicated by the security context indicates the context for the function's name resolution
    request.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wsk-client">WSK_CLIENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nf-wsk-wskcaptureprovidernpi">WskCaptureProviderNPI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_free_address_info">WskFreeAddressInfo</a>
 

 

