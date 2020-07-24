---
UID: NC:ndis.MINIPORT_REMOVE_DEVICE
title: MINIPORT_REMOVE_DEVICE (ndis.h)
description: The MiniportRemoveDevice function releases resources that the MiniportAddDevice function allocated.
old-location: netvista\miniportremovedevice.htm
tech.root: netvista
ms.assetid: 24dd887b-575f-4790-bb53-7c3fb825bd61
ms.date: 05/02/2018
keywords: ["MINIPORT_REMOVE_DEVICE callback function"]
ms.keywords: MINIPORT_REMOVE_DEVICE, MINIPORT_REMOVE_DEVICE callback, MiniportRemoveDevice, MiniportRemoveDevice callback function [Network Drivers Starting with Windows Vista], ndis/MiniportRemoveDevice, ndis_msix_ref_daeef188-96e7-4917-b37f-2af8ba18eda9.xml, netvista.miniportremovedevice
f1_keywords:
 - "ndis/MiniportRemoveDevice"
 - "MiniportRemoveDevice"
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- MiniportRemoveDevice
targetos: Windows
req.typenames: 
---

# MINIPORT_REMOVE_DEVICE callback function


## -description


The 
   <i>MiniportRemoveDevice</i> function releases resources that the 
   <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_add_device">MiniportAddDevice</a> function
   allocated.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_REMOVE_DEVICE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportAddDeviceContext [in]

A handle for a driver-allocated context area that the miniport driver registered with NDIS in the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_add_device">MiniportAddDevice</a> function.


## -remarks



The 
    <i>MiniportRemoveDevice</i> function is an optional function. Miniport drivers that
    support MSI-X should specify an entry point for this function in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_pnp_characteristics">
    NDIS_MINIPORT_PNP_CHARACTERISTICS</a> structure.

When NDIS receives a request from the Plug and Play (PnP) manager to remove a device, NDIS calls the 
    <i>MiniportRemoveDevice</i> function. 
    <i>MiniportRemoveDevice</i> should then undo the operations that the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_add_device">MiniportAddDevice</a> function
    performed.

Miniport adapters might be halted and initialized several times before NDIS calls 
    <i>MiniportRemoveDevice</i>. If NDIS called 
    <i>MiniportAddDevice</i> and it returned NDIS_STATUS_SUCCESS, NDIS will not call 
    <i>MiniportAddDevice</i> for the same miniport adapter before calling 
    <i>MiniportRemoveDevice</i> for that adapter.

NDIS calls 
    <i>MiniportRemoveDevice</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportRemoveDevice</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportRemoveDevice</i> function that is named "MyRemoveDevice", use the <b>MINIPORT_REMOVE_DEVICE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_REMOVE_DEVICE MyRemoveDevice;</pre>
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
 MyRemoveDevice(
    NDIS_HANDLE  MiniportAddDeviceContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_REMOVE_DEVICE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_REMOVE_DEVICE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_add_device">MiniportAddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_init_parameters">NDIS_MINIPORT_INIT_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_pnp_characteristics">
   NDIS_MINIPORT_PNP_CHARACTERISTICS</a>
 

 

