---
UID: NC:ndis.PROTOCOL_CM_DEREGISTER_SAP
title: PROTOCOL_CM_DEREGISTER_SAP (ndis.h)
description: The ProtocolCmDeregisterSap function is required.
old-location: netvista\protocolcmderegistersap.htm
tech.root: netvista
ms.assetid: 738c426e-aa4f-4f59-b955-fbf67071303f
ms.date: 05/02/2018
ms.keywords: PROTOCOL_CM_DEREGISTER_SAP, PROTOCOL_CM_DEREGISTER_SAP callback, ProtocolCmDeregisterSap, ProtocolCmDeregisterSap callback function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_fce09df2-cd92-4c6e-8596-91ecdb5f0c2c.xml, ndis/ProtocolCmDeregisterSap, netvista.protocolcmderegistersap
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolCmDeregisterSap (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolCmDeregisterSap (NDIS   5.1)) in Windows XP.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- ProtocolCmDeregisterSap
product:
- Windows
targetos: Windows
req.typenames: 
---

# PROTOCOL_CM_DEREGISTER_SAP callback function


## -description


The 
  <i>ProtocolCmDeregisterSap</i> function is required. This function is called by NDIS to request that a call
  manager deregister a SAP on behalf of a connection-oriented client.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CM_DEREGISTER_SAP</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters




### -param CallMgrSapContext [in]

Specifies the handle to a call manager-allocated context area in which the call manager maintains
     its per-SAP state information. The call manager supplied this handle to NDIS from its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cm_reg_sap">
     ProtocolCmRegisterSap</a> function.


## -returns



<i>ProtocolCmDeregisterSap</i> returns the status of its operation(s) as one of the following:

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
Indicates that the call manager successfully removed the SAP registration and freed any
       resources allocated to maintain per-SAP information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the call manager will complete the request to deregister the SAP asynchronously.
       The call manager must call 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscmderegistersapcomplete">
       NdisCmDeregisterSapComplete</a> to signal NDIS when the operation is complete.

</td>
</tr>
</table>
 




## -remarks



<i>ProtocolCmDeregisterSap</i> communicates with network control devices or other media-specific agents,
    as necessary, to deregister the SAP on the network. Such actions could include, but are not limited
    to:

<ul>
<li>
Communicating with a switching hardware

</li>
<li>
Communicating with a network control station

</li>
<li>
Communicating with other media-specific network agents

</li>
</ul>
If a call manager is required to communicate with networking control agents, such as a network switch,
    it should use a virtual connection to the network control agent that it established in its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a> function.
    Stand-alone call managers communicate through the underlying miniport driver by calling 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscosendnetbufferlists">NdisCoSendNetBufferLists</a>.
    Miniport drivers that provide integrated call-management support never call 
    <b>NdisCoSendNetBufferLists</b>. Instead, they transmit the data directly across the network.

In addition, 
    <i>ProtocolCmDeregisterSap</i> must free any dynamically-allocated resources in its per-SAP area, provided
    at 
    <i>CallMgrSapContext</i>, as well as freeing the state area itself before returning control to NDIS.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolCmDeregisterSap</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCmDeregisterSap</i> function that is named "MyCmDeregisterSap", use the <b>PROTOCOL_CM_DEREGISTER_SAP</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CM_DEREGISTER_SAP MyCmDeregisterSap;</pre>
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
 MyCmDeregisterSap(
    NDIS_HANDLE  CallMgrSapContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CM_DEREGISTER_SAP</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CM_DEREGISTER_SAP</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscmderegistersapcomplete">NdisCmDeregisterSapComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscosendnetbufferlists">NdisCoSendNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cm_reg_sap">ProtocolCmRegisterSap</a>
 

 

