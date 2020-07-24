---
UID: NS:windot11._DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS
title: _DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS (windot11.h)
description: The response parameters for a provision discovery response are specified in a DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS structure. This structure is sent with an OID_DOT11_WFD_SEND_PROVISION_DISCOVERY_RESPONSE request to the miniport.
old-location: netvista\dot11_received_provision_discovery_response_parameters.htm
tech.root: netvista
ms.assetid: 5D084A9F-B0B1-4DB6-91CF-8185063A1D65
ms.date: 02/16/2018
keywords: ["_DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS structure"]
ms.keywords: "*PDOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS, DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS, DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS structure [Network Drivers Starting with Windows Vista], PDOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS, PDOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS, netvista.dot11_received_provision_discovery_response_parameters, windot11/DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS, windot11/PDOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS"
f1_keywords:
 - "windot11/DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS"
 - "DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS"
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with   Windows 8.
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
- Windot11.h
api_name:
- DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS
targetos: Windows
req.typenames: DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS, *PDOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS
product:
- Windows 10 or later.
---

# _DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The response parameters for a provision discovery response are specified in a <b>DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS</b> structure. This structure is sent with an <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-wfd-send-provision-discovery-response">OID_DOT11_WFD_SEND_PROVISION_DISCOVERY_RESPONSE</a> request to the miniport.


## -syntax


```cpp
typedef struct _DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  DOT11_MAC_ADDRESS  TransmitterDeviceAddress;
  DOT11_MAC_ADDRESS  BSSID;
  DOT11_DIALOG_TOKEN DialogToken;
  ULONG              uIEsOffset;
  ULONG              uIEsLength;
} DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS, *PDOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS;
```


## -struct-fields




### -field Header

The type, revision, and size of the <b>DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS</b> structure. The required settings for the members of <b>Header</b> are the following.

<table>
<tr>
<th>Member</th>
<th>Setting</th>
</tr>
<tr>
<td><b>Type</b></td>
<td>NDIS_OBJECT_TYPE_DEFAULT</td>
</tr>
<tr>
<td><b>Revision</b></td>
<td>DOT11_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_RECEIVED_PROVISION_DISCOVERY_RESPONSE_PARAMETERS_REVISION_1</td>
</tr>
</table>
 


### -field TransmitterDeviceAddress

The address of the device that transmitted the provision discovery response packet.


### -field BSSID

The BSSID from the received provision discovery response packet.


### -field DialogToken

The dialog token from the received provision discovery response packet.


### -field uIEsOffset

The offset, in bytes,  of the array of additional information elements (IEs) received in the provision discovery response packet. This offset is from the start of the buffer that contains this structure.


### -field uIEsLength

The length, in bytes, of the array of IEs provided at <b>uIEsOffset</b>.


## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-wfd-send-provision-discovery-response">OID_DOT11_WFD_SEND_PROVISION_DISCOVERY_RESPONSE</a>



 

 


