---
UID: NC:wsk.PFN_WSK_SEND_TO
title: PFN_WSK_SEND_TO (wsk.h)
description: The WskSendTo function sends datagram data to a remote transport address.
old-location: netvista\wsksendto.htm
tech.root: netvista
ms.assetid: 34257ef2-947a-463a-b234-04fbaffa9344
ms.date: 05/02/2018
keywords: ["PFN_WSK_SEND_TO callback function"]
ms.keywords: PFN_WSK_SEND_TO, PFN_WSK_SEND_TO callback, WskSendTo, WskSendTo callback function [Network Drivers Starting with Windows Vista], netvista.wsksendto, wsk/WskSendTo, wskref_9e00d25c-f00b-4656-8e67-37a22bd36a16.xml
f1_keywords:
 - "wsk/WskSendTo"
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Universal
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
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- wsk.h
api_name:
- WskSendTo
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_WSK_SEND_TO callback function


## -description


The 
  <b>WskSendTo</b> function sends datagram data to a remote transport address.


## -parameters




### -param Socket [in]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_socket">WSK_SOCKET</a> structure that specifies the socket
     object for the datagram socket over which to send the datagram.


### -param Buffer [in]

A pointer to an initialized 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_buf">WSK_BUF</a> structure that describes the data buffer
     that contains the datagram that is being sent over the socket.


### -param Flags

This parameter is reserved for system use. A WSK application must set this parameter to
     zero.


### -param RemoteAddress [in, optional]

A pointer to a structure that specifies the remote transport address to which to send the
     datagram. This pointer must be a pointer to the specific SOCKADDR structure type that corresponds to the
     address family that the WSK application specified when it created the socket.
     

If the WSK application has set either a fixed remote transport address or a fixed destination
     transport address for the datagram socket, this pointer is optional and may be <b>NULL</b>. If <b>NULL</b>, the
     datagram is sent to the fixed remote transport address or the fixed destination transport address. If
     non-<b>NULL</b>, the datagram is sent to the specified remote transport address.

For more information about setting a fixed remote transport address for a datagram socket, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/sio-wsk-set-remote-address">
     SIO_WSK_SET_REMOTE_ADDRESS</a>.

For more information about setting a fixed destination transport address for a datagram socket, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/sio-wsk-set-sendto-address">
     SIO_WSK_SET_SENDTO_ADDRESS</a>.


### -param ControlInfoLength [in]

The number of bytes of data in the buffer that is pointed to by the 
     <i>ControlInfo</i> parameter. If there is no control information associated with the datagram, the 
     <i>ControlInfoLength</i> parameter must be zero.


### -param ControlInfo [in, optional]

A pointer to a buffer that contains control information that is associated with the datagram that
     is being sent. The control information data consists of one or more control data objects, each of which
     begins with a 
     <a href="https://docs.microsoft.com/windows/desktop/api/ws2def/ns-ws2def-_wsacmsghdr">CMSGHDR</a> structure. If there is no control
     information that is associated with the datagram, this parameter should be <b>NULL</b>.


### -param Irp [in, out]

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the send operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions">Using IRPs with Winsock
     Kernel Functions</a>.


## -returns



<b>WskSendTo</b> returns one of the following NTSTATUS codes:

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
The datagram was successfully sent over the socket. The IRP will be completed with success
       status. The 
       <b>IoStatus.Information</b> field of the IRP contains the number of bytes that were sent.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The WSK subsystem could not send the datagram over the socket immediately. The WSK subsystem
       will complete the IRP after it has sent the datagram over the socket. The status of the send operation
       will be returned in the 
       <b>IoStatus.Status</b> field of the IRP. If the operation succeeds, the 
       <b>IoStatus.Information</b> field of the IRP will contain the number of bytes that were sent.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FILE_FORCED_CLOSED</b></dt>
</dl>
</td>
<td width="60%">
The socket is no longer functional. The IRP will be completed with failure status. The WSK
       application must call the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_close_socket">WskCloseSocket</a> function to close the
       socket as soon as possible.

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



If the 
    <b>WskSendTo</b> function returns STATUS_PENDING, the MDL chain that is described in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_buf">WSK_BUF</a> structure that is pointed to by the 
    <i>Buffer</i> parameter must remain locked in memory until the IRP is completed. In addition, the buffer
    that is pointed to by the 
    <i>ControlInfo</i> parameter must also remain valid until the IRP is completed. If the WSK application
    allocated the MDL chain or the control information buffer with one of the 
    <b>ExAllocate<i>Xxx</i></b> functions, it cannot free the memory with the corresponding 
    <b>ExFree<i>Xxx</i></b> function until after the IRP is completed. If the WSK application allocated the MDL chain or
    the control information buffer on the stack, it cannot return from the function that calls the 
    <b>WskSendTo</b> function until after the IRP is completed.

The WSK subsystem does not perform any buffering of data when it sends datagrams over a socket.
    Therefore, a call to the 
    <b>WskSendTo</b> function will not be completed by the WSK subsystem until all of the data has actually
    been sent.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ws2def/ns-ws2def-_wsacmsghdr">CMSGHDR</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ws2def/ns-ws2def-sockaddr">SOCKADDR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_buf">WSK_BUF</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_provider_datagram_dispatch">
   WSK_PROVIDER_DATAGRAM_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_socket">WSK_SOCKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_close_socket">WskCloseSocket</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_control_socket">WskControlSocket</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_receive_from">WskReceiveFrom</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_receive_from_event">WskReceiveFromEvent</a>
 

 

