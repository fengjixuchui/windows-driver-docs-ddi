---
UID: NS:ndiswwan._NDIS_WWAN_SET_RADIO_STATE
title: _NDIS_WWAN_SET_RADIO_STATE (ndiswwan.h)
description: The NDIS_WWAN_SET_RADIO_STATE structure represents the power action to take on the MB device's radio.
old-location: netvista\ndis_wwan_set_radio_state.htm
tech.root: netvista
ms.assetid: 4fe42397-1c95-4017-8d7b-14eda11c7b74
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_SET_RADIO_STATE, NDIS_WWAN_SET_RADIO_STATE, NDIS_WWAN_SET_RADIO_STATE structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_SET_RADIO_STATE, PNDIS_WWAN_SET_RADIO_STATE structure pointer [Network Drivers Starting with Windows Vista], WwanRef_b5525c3b-fbf3-4423-b691-464ed9a7a65a.xml, _NDIS_WWAN_SET_RADIO_STATE, ndiswwan/NDIS_WWAN_SET_RADIO_STATE, ndiswwan/PNDIS_WWAN_SET_RADIO_STATE, netvista.ndis_wwan_set_radio_state"
ms.topic: struct
f1_keywords:
 - "ndiswwan/NDIS_WWAN_SET_RADIO_STATE"
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
- NDIS_WWAN_SET_RADIO_STATE
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_SET_RADIO_STATE, *PNDIS_WWAN_SET_RADIO_STATE
---

# _NDIS_WWAN_SET_RADIO_STATE structure


## -description


The NDIS_WWAN_SET_RADIO_STATE structure represents the power action to take on the MB device's
  radio.


## -struct-fields




### -field Header

The header with type, revision, and size information about the NDIS_WWAN_SET_RADIO_STATE
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
NDIS_WWAN_SET_RADIO_STATE_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_SET_RADIO_STATE)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field RadioAction

A value from the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_radio">WWAN_RADIO</a> enumeration that represents the power
     action to take on the MB device's radio. The following table shows the possible values for this member.
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WwanRadioOn

</td>
<td>
Turn on radio.

</td>
</tr>
<tr>
<td>
WwanRadioOff

</td>
<td>
Turn off radio.

</td>
</tr>
</table>
 


## -remarks



This parameter allows Windows to turn the radio power on and off. Be aware that this affects only the 
    <b>SwRadioState</b> .




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_radio">WWAN_RADIO</a>
 

 

