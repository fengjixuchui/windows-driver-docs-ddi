---
UID: NC:ndis.FILTER_ATTACH
title: FILTER_ATTACH (ndis.h)
description: NDIS calls a filter driver's FilterAttach function to allocate and initialize a filter module's data structures.Note  You must declare the function by using the FILTER_ATTACH type.
old-location: netvista\filterattach.htm
tech.root: netvista
ms.assetid: 0a15a8c9-74af-4d93-bd12-a3c81c177684
ms.date: 05/02/2018
ms.keywords: FILTER_ATTACH, FILTER_ATTACH callback, FilterAttach, FilterAttach callback function [Network Drivers Starting with Windows Vista], filter_functions_ref_1e3f64d6-a779-4732-824a-87af6a7adc25.xml, ndis/FilterAttach, netvista.filterattach
ms.topic: callback
f1_keywords:
 - "ndis/FilterAttach"
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
- ndis.h
api_name:
- FilterAttach
product:
- Windows
targetos: Windows
req.typenames: 
---

# FILTER_ATTACH callback function


## -description


NDIS calls a filter driver's 
  <i>FilterAttach</i> function to allocate and initialize a filter module's data structures.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>FILTER_ATTACH</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param NdisFilterHandle [in]

An NDIS handle that identifies a filter module. The filter driver must save this handle. The
     handle is required in subsequent calls to 
     <b>NdisF<i>Xxx</i></b> functions.


### -param FilterDriverContext [in]

The handle that the driver passed to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">
     NdisFRegisterFilterDriver</a> function that identifies the driver context area.


### -param AttachParameters [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_filter_attach_parameters">
     NDIS_FILTER_ATTACH_PARAMETERS</a> structure that defines the initialization parameters for the filter
     module.


## -returns



<i>FilterAttach</i> returns one of the following status values:

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
<i>FilterAttach</i> successfully allocated and initialized data structures for this filter
       module.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<i>FilterAttach</i> failed because of insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
<i>FilterAttach</i> returns NDIS_STATUS_FAILURE if none of the preceding values applies. The filter
       driver should call the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteeventlogentry">NdisWriteEventLogEntry</a> function
       together with parameters that specify the reason for the failure.

</td>
</tr>
</table>
 




## -remarks



<i>FilterAttach</i> is a required function. NDIS calls a filter driver's 
    <i>FilterAttach</i> function when the specified filter module is in the 
    <i>Detached</i> state. NDIS can call 
    <i>FilterAttach</i> at any time after the call to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">FilterSetOptions</a> function returns.

At the start of execution in 
    <i>FilterAttach</i>, the filter module enters the 
    <i>Attaching</i> state.

Filter drivers should avoid issuing unnecessary OID queries. Instead, use the information in 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_filter_attach_parameters">
    NDIS_FILTER_ATTACH_PARAMETERS</a>, when available, to obtain information about underlying drivers.

A filter driver performs the following operations when NDIS calls 
    <i>FilterAttach</i>.

<ul>
<li>
Creates a context area for the filter module and allocates buffer pools and any other resources.

</li>
<li>
Calls the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfsetattributes">NdisFSetAttributes</a> function together
      with the 
      <i>NdisFilterHandle</i> that NDIS passed to 
      <i>FilterAttach</i>. The 
      <i>FilterModuleContext</i> parameter of 
      <b>NdisFSetAttributes</b> specifies the filter driver's context area for this filter module. NDIS passes
      this context area to the filter driver's 
      <i>FilterXxx</i> functions.

</li>
<li>
Optionally reads configuration parameters from the registry.

</li>
<li>
If the preceding operations completed successfully, the filter module enters the 
      <i>Paused</i> state.

</li>
<li>
If the preceding operations failed, the filter driver must release any resources that it allocated
      in the 
      <i>FilterAttach</i> function and return the filter module to the 
      <i>Detached</i> state.

</li>
<li>
Returns NDIS_STATUS_SUCCESS or an appropriate failure code.

</li>
</ul>
A filter driver should not make send requests, indicate received data, make OID requests, or make
    status indications from the 
    <i>Attaching</i> state.

NDIS calls a filter driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_detach">FilterDetach</a> function to release all the
    resources that are associated with a filter module and return the filter module to the 
    <i>Detached</i> state.

NDIS calls 
    <i>FilterAttach</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>FilterAttach</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterAttach</i> function that is named "MyAttach", use the <b>FILTER_ATTACH</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>FILTER_ATTACH MyAttach;</pre>
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
 MyAttach(
    NDIS_HANDLE  NdisFilterHandle,
    NDIS_HANDLE  FilterDriverContext,
    PNDIS_FILTER_ATTACH_PARAMETERS  AttachParameters
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>FILTER_ATTACH</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_ATTACH</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_detach">FilterDetach</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">FilterSetOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_filter_attach_parameters">NDIS_FILTER_ATTACH_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">NdisFRegisterFilterDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfsetattributes">NdisFSetAttributes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteeventlogentry">NdisWriteEventLogEntry</a>
 

 

