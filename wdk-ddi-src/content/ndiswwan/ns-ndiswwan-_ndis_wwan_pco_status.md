---
UID: NS:ndiswwan._NDIS_WWAN_PCO_STATUS
title: _NDIS_WWAN_PCO_STATUS (ndiswwan.h)
description: The NDIS_WWAN_PCO_STATUS structure represents the Protocol Configuration Option (PCO) status of the modem.
old-location: netvista\ndis_wwan_pco_status.htm
tech.root: netvista
ms.assetid: C71187C5-74B6-450A-8461-BB9FDF60DB8D
ms.date: 05/02/2018
ms.keywords: "*PNDIS_WWAN_PCO_STATUS, NDIS_WWAN_PCO_STATUS, NDIS_WWAN_PCO_STATUS structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_PCO_STATUS, PNDIS_WWAN_PCO_STATUS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_PCO_STATUS, ndiswwan/NDIS_WWAN_PCO_STATUS, ndiswwan/PNDIS_WWAN_PCO_STATUS, netvista.ndis_wwan_pco_status"
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
- NDIS_WWAN_PCO_STATUS
product:
- Windows
targetos: Windows
req.typenames: NDIS_WWAN_PCO_STATUS, *PNDIS_WWAN_PCO_STATUS
---

# _NDIS_WWAN_PCO_STATUS structure


## -description


The <b>NDIS_WWAN_PCO_STATUS</b> structure represents the Protocol Configuration Option (PCO) status of the modem.


## -struct-fields




### -field Header

The header with type, revision, and size information about the <b>NDIS_WWAN_PCO_STATUS</b> structure.
     The MB Service sets the header with the values that are shown in the following table when it sends the
     data structure to the miniport driver for 
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
NDIS_WWAN_PCO_STATUS_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_PCO_STATUS)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of system capability. The following table shows the possible values for
     this member.
     

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WWAN_STATUS_SUCCESS

</td>
<td>
The PCO value operation succeeded.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_CONTEXT_NOT_ACTIVATED

</td>
<td>
TThe PCO value is not available because the PDP context is not activated.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NO_DEVICE_SUPPORT

</td>
<td>
The PCO operation is not supported by the modem.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NOT_REGISTERED

</td>
<td>
The PCO value is not available because the modem is not registered.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_PACKET_SVC_DETACHED

</td>
<td>
The PCO value is not available because no packet service is attached.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_RADIO_POWER_OFF

</td>
<td>
The PCO value not available because the radio is in the OFF state.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_BUSY

</td>
<td>
PCO value is not available because the modem is busy.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NOT_INITIALIZED

</td>
<td>
TThe PCO value is not available because the device is initializing. Retry after the ready-state has changed to <b>WwanReadyStateInitialized.</b>

</td>
</tr>
<tr>
<td>
WWAN_STATUS_NOT_ACTIVATED

</td>
<td>
The PCO value is not available because the service is not activated.

</td>
</tr>
<tr>
<td>
WWAN_STATUS_READ_FAILURE

</td>
<td>
The PCO value failed due to a read failure.

</td>
</tr>
</table>
 


### -field PcoValue

A formatted <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_pco_value">WWAN_PCO_VALUE</a> structure, which contains the PCO information payload from the network as defined in the 3GPP TS24.008 spec.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-protocol-configuration-options-pco-operations">MB Protocol Configuration Options (PCO) operations</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-wwan-pco-status">NDIS_STATUS_WWAN_PCO_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-pco">OID_WWAN_PCO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_pco_value">WWAN_PCO_VALUE</a>
 

 

