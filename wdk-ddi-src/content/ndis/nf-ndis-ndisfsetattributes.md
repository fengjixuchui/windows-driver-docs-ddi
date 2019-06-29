---
UID: NF:ndis.NdisFSetAttributes
title: NdisFSetAttributes function (ndis.h)
description: A filter driver calls the NdisFSetAttributes function to specify a filter module context area.
old-location: netvista\ndisfsetattributes.htm
tech.root: netvista
ms.assetid: 66e20ac3-e97d-429d-868e-79c04881702b
ms.date: 05/02/2018
ms.keywords: NdisFSetAttributes, NdisFSetAttributes function [Network Drivers Starting with Windows Vista], filter_ndis_functions_ref_67ad6b8c-e7ae-45d7-9213-48e8a2b6c2ff.xml, ndis/NdisFSetAttributes, netvista.ndisfsetattributes
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Filter_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisFSetAttributes
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFSetAttributes function


## -description


A filter driver calls the 
  <b>NdisFSetAttributes</b> function to specify a filter module context area.


## -parameters




### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_attach">FilterAttach</a> function.


### -param FilterModuleContext [in]

The caller-allocated context area for this filter module.


### -param FilterAttributes [in]

A pointer to a filter driver allocated 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_filter_attributes">
     NDIS_FILTER_ATTRIBUTES</a> structure.


## -returns



<b>NdisFSetAttributes</b> returns one of the following status values:

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
<b>NdisFSetAttributes</b> returns NDIS_STATUS_SUCCESS if it set the filter driver attributes.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisFSetAttributes</b> failed because of insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisFSetAttributes</b> returns NDIS_STATUS_FAILURE if none of the preceding values applies.

</td>
</tr>
</table>
 




## -remarks



A filter driver calls 
    <b>NdisFSetAttributes</b> from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_attach">FilterAttach</a> function and passes the
    handle that NDIS passed to 
    <i>FilterAttach</i> at the 
    <i>NdisFilterHandle</i> parameter. The 
    <i>FilterModuleContext</i> parameter of 
    <b>NdisFSetAttributes</b> specifies the context area for this filter module. NDIS passes the context area
    back to the filter driver in calls to functions such as 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_send_net_buffer_lists">FilterSendNetBufferLists</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_send_net_buffer_lists">FilterSendNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_filter_attributes">NDIS_FILTER_ATTRIBUTES</a>
 

 

