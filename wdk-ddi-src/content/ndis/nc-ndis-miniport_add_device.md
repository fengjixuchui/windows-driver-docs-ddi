---
UID: NC:ndis.MINIPORT_ADD_DEVICE
title: MINIPORT_ADD_DEVICE (ndis.h)
description: The MiniportAddDevice function enables a miniport driver to establish a context area for an added device.
old-location: netvista\miniportadddevice.htm
tech.root: netvista
ms.assetid: 50e04b5a-e430-484c-aabb-cc7b9ecb53b0
ms.date: 05/02/2018
ms.keywords: MINIPORT_ADD_DEVICE, MINIPORT_ADD_DEVICE callback, MiniportAddDevice, MiniportAddDevice callback function [Network Drivers Starting with Windows Vista], ndis/MiniportAddDevice, ndis_msix_ref_60df66e2-2e17-4bd1-8793-8310326d883d.xml, netvista.miniportadddevice
ms.topic: callback
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
- MiniportAddDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_ADD_DEVICE callback function


## -description


The 
   <i>MiniportAddDevice</i> function enables a miniport driver to establish a context area
   for an added device.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_ADD_DEVICE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param NdisMiniportHandle [in]

An NDIS handle that identifies the miniport adapter that the Plug and Play (PnP) manager is
     adding. NDIS also passes this handle to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">
     MiniportInitializeEx</a> function.


### -param MiniportDriverContext [in]

A handle to a driver-allocated context area where the driver maintains state and configuration
     information. The miniport driver passed this context area to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismregisterminiportdriver">
     NdisMRegisterMiniportDriver</a> function.


## -returns



<i>MiniportAddDevice</i> returns one of the following values:

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
The miniport driver successfully allocated the resources that it requires to add the
       device.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver failed to allocate the required resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_add_device">MiniportAddDevice</a> failed for reasons other than insufficient
       resources.

</td>
</tr>
</table>
 

If 
     <i>MiniportAddDevice</i> fails, NDIS will not call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function
     to initialize the miniport adapter.




## -remarks



The 
    <i>MiniportAddDevice</i> function is an optional function. Miniport drivers that
    support MSI-X should specify an entry point for this function in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_pnp_characteristics">
    NDIS_MINIPORT_PNP_CHARACTERISTICS</a> structure.

<i>MiniportAddDevice</i> can allocate a context area for handling 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-filter-resource-requirements">
    IRP_MN_FILTER_RESOURCE_REQUIREMENTS</a> I/O request packets (IRPs) that the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_pnp_irp">
    MiniportFilterResourceRequirements</a> function handles. Miniport drivers specify the context area by
    initializing an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_add_device_registration_attributes">
    NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES</a> structure and then calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismsetminiportattributes">
    NdisMSetMiniportAttributes</a> function. NDIS later provides this context handle to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_remove_device">MiniportRemoveDevice</a>, 
    <i>
    MiniportFilterResourceRequirements</i>, 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_pnp_irp">MiniportStartDevice</a>, and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> functions.
    For 
    <i>MiniportInitializeEx</i>, the context handle is passed in the 
    <b>MiniportAddDeviceContext</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_init_parameters">
    NDIS_MINIPORT_INIT_PARAMETERS</a> structure that the 
    <i>MiniportInitParameters</i> parameter points to.

If the miniport driver fails the 
    <i>MiniportAddDevice</i> call after it allocated the context area, the driver must
    free the context area before returning from 
    <i>MiniportAddDevice</i>.

Miniport drivers should use a different context area for the 
    <b>MiniportAddDeviceContext</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_add_device_registration_attributes">NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES</a> structure
    and the 
    <b>MiniportAdapterContext</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_init_parameters">NDIS_MINIPORT_INIT_PARAMETERS</a> structure. Separate context
    areas will ensure that information in the context area is not reinitialized, which might occur in the 
    <i>MiniportInitializeEx</i> function if the miniport adapter is halted and
    reinitialized.

When the PnP manager requests that NDIS remove the device, NDIS calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_remove_device">MiniportRemoveDevice</a> function to
    undo the operations that 
    <i>MiniportAddDevice</i> performed.

NDIS calls 
    <i>MiniportAddDevice</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportAddDevice</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportAddDevice</i> function that is named "MyAddDevice", use the <b>MINIPORT_ADD_DEVICE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_ADD_DEVICE MyAddDevice;</pre>
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
 MyAddDevice(
    NDIS_HANDLE  NdisMiniportHandle,
    NDIS_HANDLE  MiniportDriverContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_ADD_DEVICE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_ADD_DEVICE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-filter-resource-requirements">
   IRP_MN_FILTER_RESOURCE_REQUIREMENTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_pnp_irp">
   MiniportFilterResourceRequirements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_remove_device">MiniportRemoveDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_pnp_irp">MiniportStartDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_add_device_registration_attributes">
   NDIS_MINIPORT_ADD_DEVICE_REGISTRATION_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_init_parameters">NDIS_MINIPORT_INIT_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_pnp_characteristics">
   NDIS_MINIPORT_PNP_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>
 

 

