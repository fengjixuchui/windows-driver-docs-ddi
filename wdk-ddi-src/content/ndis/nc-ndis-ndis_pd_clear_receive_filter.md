---
UID: NC:ndis.NDIS_PD_CLEAR_RECEIVE_FILTER
title: NDIS_PD_CLEAR_RECEIVE_FILTER (ndis.h)
description: The PacketDirect (PD) platform calls a PD-capable miniport driver's NdisPDClearReceiveFilter function to clear this filter from the PD platform.
old-location: netvista\ndispdclearreceivefilter.htm
tech.root: netvista
ms.assetid: C91F2E5D-C37F-48A9-9AE0-F5A8C5D8F54D
ms.date: 05/02/2018
keywords: ["NDIS_PD_CLEAR_RECEIVE_FILTER callback function"]
ms.keywords: NDIS_PD_CLEAR_RECEIVE_FILTER, NDIS_PD_CLEAR_RECEIVE_FILTER callback, NdisPDClearReceiveFilter, NdisPDClearReceiveFilter callback function [Network Drivers Starting with Windows Vista], ndis/NdisPDClearReceiveFilter, netvista.ndispdclearreceivefilter
f1_keywords:
 - "ndis/NdisPDClearReceiveFilter"
 - "NdisPDClearReceiveFilter"
req.header: ndis.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- NdisPDClearReceiveFilter
targetos: Windows
req.typenames: 
---

# NDIS_PD_CLEAR_RECEIVE_FILTER callback function


## -description


The PacketDirect (PD) platform calls a PD-capable miniport driver's 
   <i>NdisPDClearReceiveFilter</i> function to clear this filter from the PD platform.<div class="alert"><b>Note</b>  You must declare the function by using the <b>NDIS_PD_CLEAR_RECEIVE_FILTER</b> type. For more
   information, see the following Examples section.</div>
<div> </div>



## -parameters




### -param FilterHandle [in]

A handle to a PD platform filter.


## -returns



This callback function does not return a value.




## -remarks



After this function returns, it's guaranteed that no more newly arriving packet will match this filter. However, there may still be in-flight packets that have already matched this filter and they are on their way to being placed into the target receive queue.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>NdisPDClearReceiveFilter</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>NdisPDClearReceiveFilter</i> function that is named "MyPDClearReceiveFilter", use the <b>NDIS_PD_CLEAR_RECEIVE_FILTER</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NDIS_PD_CLEAR_RECEIVE_FILTER MyPDClearReceiveFilter;</pre>
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
VOID
 MyPDClearReceiveFilter(
    NDIS_PD_FILTER_HANDLE  FilterHandle
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>NDIS_PD_CLEAR_RECEIVE_FILTER</b> function type is defined in the Ntddndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>NDIS_PD_CLEAR_RECEIVE_FILTER</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 



