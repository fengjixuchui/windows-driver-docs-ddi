---
UID: NS:wwan._WWAN_RADIO_STATE
title: _WWAN_RADIO_STATE (wwan.h)
description: The WWAN_RADIO_STATE structure represents the hardware-based and software-based radio power states of the MB device.
old-location: netvista\wwan_radio_state.htm
tech.root: netvista
ms.assetid: 15c02819-bae8-48f5-8782-97823b6907bd
ms.date: 05/02/2018
keywords: ["_WWAN_RADIO_STATE structure"]
ms.keywords: "*PWWAN_RADIO_STATE, PWWAN_RADIO_STATE, PWWAN_RADIO_STATE structure pointer [Network Drivers Starting with Windows Vista], WWAN_RADIO_STATE, WWAN_RADIO_STATE structure [Network Drivers Starting with Windows Vista], WwanRef_b1ea0ea1-b23f-4e5c-9528-659e1f6e4162.xml, _WWAN_RADIO_STATE, netvista.wwan_radio_state, wwan/PWWAN_RADIO_STATE, wwan/WWAN_RADIO_STATE"
f1_keywords:
 - "wwan/WWAN_RADIO_STATE"
req.header: wwan.h
req.include-header: Wwan.h
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
- wwan.h
api_name:
- WWAN_RADIO_STATE
product:
- Windows
targetos: Windows
req.typenames: WWAN_RADIO_STATE, *PWWAN_RADIO_STATE
---

# _WWAN_RADIO_STATE structure


## -description


The WWAN_RADIO_STATE structure represents the hardware-based and software-based radio power states of
  the MB device.


## -struct-fields




### -field HwRadioState

The hardware radio power state of the device. The MB Service cannot set this state because it is
     read-only. The following table shows the possible values for this member.
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WwanRadioOff

</td>
<td>
The hardware radio is off.

</td>
</tr>
<tr>
<td>
WwanRadioOn

</td>
<td>
The hardware radio is on, or no switch exists to control power to the hardware radio.

</td>
</tr>
</table>
 


### -field SwRadioState

The software-based radio power state of the device. The MB Service can get and set this state. The
     following table shows the possible values for this member.
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WwanRadioOff

</td>
<td>
The radio is turned off by Windows.

</td>
</tr>
<tr>
<td>
WwanRadioOn

</td>
<td>
The radio is turned on by Windows.

</td>
</tr>
</table>
 


## -remarks



Miniport drivers should continue the software-based radio power state across system restart or device
    removal and reinsertion. Miniport drivers should store the device software-based radio power state
    information and use it to set the device radio power state for each restart or reinsertion of the
    device.

The following table defines the relationship between hardware-based and software-based radio power
    state settings and their effective result.

<table>
<tr>
<th>HwRadioState value</th>
<th>SwRadioState value</th>
<th>Overall radio power state</th>
</tr>
<tr>
<td>
WwanRadioOff

</td>
<td>
WwanRadioOff

</td>
<td>
WwanRadioOff

</td>
</tr>
<tr>
<td>
WwanRadioOff

</td>
<td>
WwanRadioOn

</td>
<td>
WwanRadioOff

</td>
</tr>
<tr>
<td>
WwanRadioOn

</td>
<td>
WwanRadioOff

</td>
<td>
WwanRadioOff

</td>
</tr>
<tr>
<td>
WwanRadioOn

</td>
<td>
WwanRadioOn

</td>
<td>
WwanRadioOn

</td>
</tr>
</table>
 

The miniport driver should send all applicable status indications such as
    NDIS_STATUS_WWAN_CONTEXT_STATE, NDIS_STATUS_WWAN_PACKET_SERVICE, and NDIS_STATUS_WWAN_REGISTER_STATE
    whenever the effective radio state changes from 
    <b>WwanRadioOn</b> to 
    <b>WwanRadioOff</b> or from 
    <b>WwanRadioOff</b> to 
    <b>WwanRadioOn</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndiswwan/ns-ndiswwan-_ndis_wwan_radio_state">NDIS_WWAN_RADIO_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_radio">WWAN_RADIO</a>
 

 

