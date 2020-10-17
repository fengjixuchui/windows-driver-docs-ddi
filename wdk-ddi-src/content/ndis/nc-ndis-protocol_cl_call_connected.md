---
UID: NC:ndis.PROTOCOL_CL_CALL_CONNECTED
title: PROTOCOL_CL_CALL_CONNECTED (ndis.h)
description: The ProtocolClCallConnected function is used by connection-oriented NDIS clients that accept incoming calls.
old-location: netvista\protocolclcallconnected.htm
tech.root: netvista
ms.assetid: 675b2066-6a65-47cf-bde7-3c843f97c960
ms.date: 05/02/2018
keywords: ["PROTOCOL_CL_CALL_CONNECTED callback function"]
ms.keywords: PROTOCOL_CL_CALL_CONNECTED, PROTOCOL_CL_CALL_CONNECTED callback, ProtocolClCallConnected, ProtocolClCallConnected callback function [Network Drivers Starting with Windows Vista], condis_client_ref_ddc435b4-ff27-4ced-b513-9bba45302496.xml, ndis/ProtocolClCallConnected, netvista.protocolclcallconnected
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolClCallConnected (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolClCallConnected (NDIS   5.1)) in Windows XP.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PROTOCOL_CL_CALL_CONNECTED
 - ndis/PROTOCOL_CL_CALL_CONNECTED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - ProtocolClCallConnected
---

# PROTOCOL_CL_CALL_CONNECTED callback function


## -description

The 
  <i>ProtocolClCallConnected</i> function is used by connection-oriented NDIS clients that accept incoming
  calls. Such clients must have 
  <i>ProtocolClCallConnected</i> functions. Otherwise, such a protocol driver's registered 
  <i>ProtocolClCallConnected</i> function can simply return control.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CL_CALL_CONNECTED</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters

### -param ProtocolVcContext 

[in]
Specifies the client's handle to its per-VC context area. The client originally returned this
     handle to NDIS from its 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a> function.

## -remarks

When 
    <i>ProtocolClCallConnected</i> is called, the call manager has successfully completed the final handshake
    on an incoming call offer previously accepted by the client's 
    <i>ProtocolClIncomingCall</i> function, which already set up the call parameters for this connection at 
    <i>ProtocolVcContext</i> .

The call to 
    <i>ProtocolClCallConnected</i> indicates that data transfers, whether incoming or outgoing, now can be
    done on the VC. 
    <i>ProtocolClCallConnected</i> should ensure that the client is ready to make or accept transfers on the
    VC before it returns control.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolClCallConnected</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolClCallConnected</i> function that is named "MyClCallConnected", use the <b>PROTOCOL_CL_CALL_CONNECTED</b> type as shown in this code example:


```
PROTOCOL_CL_CALL_CONNECTED MyClCallConnected;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
VOID
 MyClCallConnected(
    NDIS_HANDLE  ProtocolVcContext
    )
  {...}
```

The <b>PROTOCOL_CL_CALL_CONNECTED</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_CALL_CONNECTED</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdispatchcallconnected">NdisCmDispatchCallConnected</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscosendnetbufferlists">NdisCoSendNetBufferLists</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdispatchcallconnected">NdisMCmDispatchCallConnected</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_call">ProtocolClIncomingCall</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_receive_net_buffer_lists">
   ProtocolCoReceiveNetBufferLists</a>