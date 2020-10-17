---
UID: NS:ndiswwan._NDIS_WWAN_DEVICE_SERVICE_COMMAND
title: _NDIS_WWAN_DEVICE_SERVICE_COMMAND (ndiswwan.h)
description: The NDIS_WWAN_DEVICE_SERVICE_COMMAND structure describes device service command data.
old-location: netvista\ndis_wwan_device_service_command.htm
tech.root: netvista
ms.assetid: 372625F8-0219-4867-909D-ACCC82F6B97C
ms.date: 05/02/2018
keywords: ["NDIS_WWAN_DEVICE_SERVICE_COMMAND structure"]
ms.keywords: "*PNDIS_WWAN_DEVICE_SERVICE_COMMAND, NDIS_WWAN_DEVICE_SERVICE_COMMAND, NDIS_WWAN_DEVICE_SERVICE_COMMAND structure [Network Drivers Starting with Windows Vista], PNDIS_WWAN_DEVICE_SERVICE_COMMAND, PNDIS_WWAN_DEVICE_SERVICE_COMMAND structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WWAN_DEVICE_SERVICE_COMMAND, ndiswwan/NDIS_WWAN_DEVICE_SERVICE_COMMAND, ndiswwan/PNDIS_WWAN_DEVICE_SERVICE_COMMAND, netvista.ndis_wwan_device_service_command"
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8 and later versions of Windows.
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
targetos: Windows
req.typenames: NDIS_WWAN_DEVICE_SERVICE_COMMAND, *PNDIS_WWAN_DEVICE_SERVICE_COMMAND
f1_keywords:
 - _NDIS_WWAN_DEVICE_SERVICE_COMMAND
 - ndiswwan/_NDIS_WWAN_DEVICE_SERVICE_COMMAND
 - PNDIS_WWAN_DEVICE_SERVICE_COMMAND
 - ndiswwan/PNDIS_WWAN_DEVICE_SERVICE_COMMAND
 - NDIS_WWAN_DEVICE_SERVICE_COMMAND
 - ndiswwan/NDIS_WWAN_DEVICE_SERVICE_COMMAND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndiswwan.h
api_name:
 - NDIS_WWAN_DEVICE_SERVICE_COMMAND
---

# _NDIS_WWAN_DEVICE_SERVICE_COMMAND structure


## -description

The NDIS_WWAN_DEVICE_SERVICE_COMMAND structure describes device service command data.

## -struct-fields

### -field Header

The header with type, revision, and size information about the NDIS_WWAN_DEVICE_SERVICE_COMMAND structure. The MB
     Service sets the header with the values that are shown in the following table when it sends the data
     structure to the miniport driver for 
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
NDIS_WWAN_DEVICE_SERVICE_COMMAND_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_DEVICE_SERVICE_COMMAND)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>.

### -field Command

The device service command.

## -see-also

<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_device_service_command">WWAN_DEVICE_SERVICE_COMMAND</a>