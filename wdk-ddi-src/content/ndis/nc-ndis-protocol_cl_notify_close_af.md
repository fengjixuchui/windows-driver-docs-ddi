---
UID: NC:ndis.PROTOCOL_CL_NOTIFY_CLOSE_AF
title: PROTOCOL_CL_NOTIFY_CLOSE_AF (ndis.h)
description: The ProtocolClNotifyCloseAf function notifies a CoNDIS client that the client should close the associated address family (AF).Note  You must declare the function by using the PROTOCOL_CL_NOTIFY_CLOSE_AF type.
old-location: netvista\protocolclnotifycloseaf.htm
tech.root: netvista
ms.assetid: 0f595daa-9822-4ca6-8f25-e6f82030d4ea
ms.date: 05/02/2018
keywords: ["PROTOCOL_CL_NOTIFY_CLOSE_AF callback function"]
ms.keywords: PROTOCOL_CL_NOTIFY_CLOSE_AF, PROTOCOL_CL_NOTIFY_CLOSE_AF callback, ProtocolClNotifyCloseAf, ProtocolClNotifyCloseAf callback function [Network Drivers Starting with Windows Vista], condis_client_ref_0b778346-7d48-4d72-807d-16d8be2da913.xml, ndis/ProtocolClNotifyCloseAf, netvista.protocolclnotifycloseaf
f1_keywords:
 - "ndis/ProtocolClNotifyCloseAf"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- ProtocolClNotifyCloseAf
product:
- Windows
targetos: Windows
req.typenames: 
---

# PROTOCOL_CL_NOTIFY_CLOSE_AF callback function


## -description


The 
  <i>ProtocolClNotifyCloseAf</i> function
  notifies a CoNDIS client that the client should close the associated address family (AF).
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CL_NOTIFY_CLOSE_AF</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters




### -param ClientAfContext








#### - ProtocolAfContext [in]

A client-supplied handle to its context area for the associated AF. The client allocated this
     context area and passed this handle to NDIS in its call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclopenaddressfamilyex">
     NdisClOpenAddressFamilyEx</a> function.


## -returns



<i>ProtocolClNotifyCloseAf</i> can
     return one of the following:

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
The client successfully closed the address family.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The client is handling this request asynchronously, and it will call the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclnotifycloseaddressfamilycomplete">
       NdisClNotifyCloseAddressFamilyComplete</a> function when the close operation is complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_<i>XXX</i></b></dt>
</dl>
</td>
<td width="60%">
The client failed the request for some driver-determined reason.

</td>
</tr>
</table>
 




## -remarks



The 
    <i>
    ProtocolClNotifyCloseAf</i> function is required for CoNDIS clients. NDIS calls 
    <i>ProtocolClNotifyCloseAf</i> when a
    call manager notifies NDIS that the address family (AF) that the 
    <i>ProtocolAfContext</i> parameter specifies should be closed. In response, the client
    should:

<ol>
<li>
Call the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscldropparty">NdisClDropParty</a> function as many times
      as necessary until only a single party remains active on each multipoint virtual connection (VC), if
      the client has any active multipoint connections.

</li>
<li>
Call the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclclosecall">NdisClCloseCall</a> function as many times
      as necessary to close all of the calls that are still open and are associated with the AF.

</li>
<li>
Call the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclderegistersap">NdisClDeregisterSap</a> function as many
      times as necessary to deregister all service access points (SAPs) that the client has registered with
      the call manager.

</li>
<li>
Call the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclcloseaddressfamily">
      NdisClCloseAddressFamily</a> function to close the AF.

</li>
</ol>
The client can complete these actions asynchronously by returning NDIS_STATUS_PENDING. If the client
    completes the call asynchronously, it must subsequently call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclnotifycloseaddressfamilycomplete">
    NdisClNotifyCloseAddressFamilyComplete</a> function when the close operation is complete. If the client
    does not return NDIS_STATUS_PENDING, the close operation is complete when 
    <i>
    ProtocolClNotifyCloseAf</i> returns.

NDIS calls 
    <i>ProtocolClNotifyCloseAf</i> at IRQL
    <= DISPATCH_LEVEL.

The client may use the 
    <i>NdisAfHandle</i> while the AF is open or while a 
    <i>
    ProtocolClNotifyCloseAf</i> operation is pending. If the 
    <i>
    ProtocolClNotifyCloseAf</i> function returns NDIS_STATUS_PENDING, use the handle in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclnotifycloseaddressfamilycomplete">
    NdisClNotifyCloseAddressFamilyComplete</a> call after the close operation completes.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolClNotifyCloseAf</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolClNotifyCloseAf</i> function that is named "MyClNotifyCloseAf", use the <b>PROTOCOL_CL_NOTIFY_CLOSE_AF</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CL_NOTIFY_CLOSE_AF MyClNotifyCloseAf;</pre>
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
 MyClNotifyCloseAf(
    NDIS_HANDLE  ProtocolAfContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CL_NOTIFY_CLOSE_AF</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_NOTIFY_CLOSE_AF</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclcloseaddressfamily">NdisClCloseAddressFamily</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclclosecall">NdisClCloseCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclderegistersap">NdisClDeregisterSap</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscldropparty">NdisClDropParty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclnotifycloseaddressfamilycomplete">
   NdisClNotifyCloseAddressFamilyComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclopenaddressfamilyex">NdisClOpenAddressFamilyEx</a>
 

 

