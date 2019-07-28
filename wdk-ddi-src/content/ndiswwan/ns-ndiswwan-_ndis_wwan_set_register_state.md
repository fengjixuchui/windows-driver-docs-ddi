---
UID: NS:ndiswwan._NDIS_WWAN_SET_REGISTER_STATE
title: _NDIS_WWAN_SET_REGISTER_STATE (ndiswwan.h)
description: The NDIS_WWAN_SET_REGISTER_STATE structure represents the network provider registration state of the MB device.
old-location: netvista\ndis_wwan_set_register_state.htm
tech.root: netvista
ms.assetid: c8d9c2aa-2eb7-43da-ae13-f7209e68e2fd
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_SET_REGISTER_STATE, NDIS_WWAN_SET_REGISTER_STATE, NDIS_WWAN_SET_REGISTER_STATE structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SET_REGISTER_STATE, PNDIS_WWAN_SET_REGISTER_STATE structure pointer [Network Drivers Starting with Windows Vista], WwanRef_272f8215-ddf9-45b0-b47c-13e12a5a22a8.xml, _NDIS_WWAN_SET_REGISTER_STATE, ndiswwan/NDIS_WWAN_SET_REGISTER_STATE, ndiswwan/PNDIS_WWAN_SET_REGISTER_STATE, netvista.ndis_wwan_set_register_state"
ms.topic: struct
f1_keywords:
 - "ndiswwan/NDIS_WWAN_SET_REGISTER_STATE"
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndiswwan.h
api_name:
- NDIS_WWAN_SET_REGISTER_STATE
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_SET_REGISTER_STATE, *PNDIS_WWAN_SET_REGISTER_STATE
---

# _NDIS_WWAN_SET_REGISTER_STATE structure


## -description


The NDIS_WWAN_SET_REGISTER_STATE structure represents the network provider registration state of the
  MB device.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SET_REGISTER_STATE
     structure. The MB Service sets the header with the values that are shown in the following table when it
     sends the data structure to the miniport driver for 
     <i>set</i> operations. Miniport drivers must set the header with the same values when they send the data
     structure to the MB service.
     

<table>
<tr>
<th>Header submember</th>
<th>Value</th>
</tr>
<tr>
<td>
Type

</td>
<td>
NDIS_OBJECT_TYPE_DEFAULT

</td>
</tr>
<tr>
<td>
Revision

</td>
<td>
NDIS_WWAN_SET_REGISTER_STATE_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SET_REGISTER_STATE)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field SetRegisterState

A formatted 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_set_register_state">WWAN_SET_REGISTER_STATE</a> object that
     represents the new network selection mode for the device.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_set_register_state">WWAN_SET_REGISTER_STATE</a>
 

 

