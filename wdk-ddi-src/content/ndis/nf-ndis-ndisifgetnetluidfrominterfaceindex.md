---
UID: NF:ndis.NdisIfGetNetLuidFromInterfaceIndex
title: NdisIfGetNetLuidFromInterfaceIndex function (ndis.h)
description: The NdisIfGetNetLuidFromInterfaceIndex function gets the NET_LUID value that is associated with a network interface index.
old-location: netvista\ndisifgetnetluidfrominterfaceindex.htm
tech.root: netvista
ms.assetid: 3cfb7f31-93ae-47a2-8da8-becfbe045f5e
ms.date: 05/02/2018
keywords: ["NdisIfGetNetLuidFromInterfaceIndex function"]
ms.keywords: NdisIfGetNetLuidFromInterfaceIndex, NdisIfGetNetLuidFromInterfaceIndex function [Network Drivers Starting with Windows Vista], ndis/NdisIfGetNetLuidFromInterfaceIndex, net_if_functions_ref_eb50b72f-9bb0-4c02-88d3-dbb0fb1d82d1.xml, netvista.ndisifgetnetluidfrominterfaceindex
f1_keywords:
 - "ndis/NdisIfGetNetLuidFromInterfaceIndex"
 - "NdisIfGetNetLuidFromInterfaceIndex"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Interfaces_Function
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
- NdisIfGetNetLuidFromInterfaceIndex
targetos: Windows
req.typenames: 
---

# NdisIfGetNetLuidFromInterfaceIndex function


## -description


The 
  <b>NdisIfGetNetLuidFromInterfaceIndex</b> function gets the 
  <a href="https://docs.microsoft.com/windows/win32/api/ifdef/ns-ifdef-net_luid_lh">NET_LUID</a> value that is associated with a network
  interface index.


## -parameters




### -param ifIndex

A network interface index that NDIS assigned to a 
     <a href="https://docs.microsoft.com/windows/win32/api/ifdef/ns-ifdef-net_luid_lh">NET_LUID</a> value in the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifregisterinterface">
     NdisIfRegisterInterface</a> function.

### -param pNetLuid [out]

A pointer to a caller-supplied NET_LUID variable. If 
     <b>NdisIfGetNetLuidFromInterfaceIndex</b> succeeds, NDIS writes the NET_LUID value that is associated
     with the specified network interface index to this variable.

## -returns



<b>NdisIfGetNetLuidFromInterfaceIndex</b> returns one of the following status values:

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
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INTERFACE_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisIfGetNetLuidFromInterfaceIndex</b> failed because the specified
       network interface index is not assigned to a registered interface.

</td>
</tr>
</table>
 




## -remarks



NDIS drivers can call the 
    <b>NdisIfGetNetLuidFromInterfaceIndex</b> function to get the 
    <a href="https://docs.microsoft.com/windows/win32/api/ifdef/ns-ifdef-net_luid_lh">NET_LUID</a> value that is associated with a network
    interface index.

For the interfaces that the NDIS proxy provider service manages, NDIS provides the interface index and
    NET_LUID in various driver initialization structures:

<ul>
<li>
Miniport drivers can obtain the interface index and NET_LUID for a miniport adapter in the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_init_parameters">
      NDIS_MINIPORT_INIT_PARAMETERS</a> structure.

</li>
<li>
Filter drivers can obtain the interface index and NET_LUID for a filter module in the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_filter_attach_parameters">
      NDIS_FILTER_ATTACH_PARAMETERS</a> structure.

</li>
<li>
Protocol drivers can obtain the interface index and NET_LUID of the highest and the lower interfaces
      on a driver stack in the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a> structure.

</li>
</ul>
NDIS assigns an interface index to a network interface when the interface provider calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifregisterinterface">NdisIfRegisterInterface</a> function.
    An interface provider calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-make-net-luid">NDIS_MAKE_NET_LUID</a> macro to create the
    NET_LUID value before it registers an interface.

The interface index value can change without a computer restart. Deregistering and re-registering an
    interface that is associated with a NET_LUID value might result in different interface index values. Do
    not confuse the interface index with the NET_LUID index that persists after a computer restarts.

NDIS provides the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifgetinterfaceindexfromnetluid">
    NdisIfGetInterfaceIndexFromNetLuid</a> function to obtain the interface index for a specified
    NET_LUID.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_bind_parameters">NDIS_BIND_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_filter_attach_parameters">NDIS_FILTER_ATTACH_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-make-net-luid">NDIS_MAKE_NET_LUID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_init_parameters">NDIS_MINIPORT_INIT_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows/win32/api/ifdef/ns-ifdef-net_luid_lh">NET_LUID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifgetinterfaceindexfromnetluid">
   NdisIfGetInterfaceIndexFromNetLuid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifregisterinterface">NdisIfRegisterInterface</a>
 

 

