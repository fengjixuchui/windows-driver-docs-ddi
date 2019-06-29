---
UID: NE:fwpsk.FWPS_FIELDS_ALE_AUTH_LISTEN_V6_
title: FWPS_FIELDS_ALE_AUTH_LISTEN_V6_ (fwpsk.h)
description: The FWPS_FIELDS_ALE_AUTH_LISTEN_V6 enumeration type specifies the data field identifiers for the FWPS_LAYER_ALE_AUTH_LISTEN_V6 and FWPS_LAYER_ALE_AUTH_LISTEN_V6_DISCARD run-time filtering layers
old-location: netvista\fwps_fields_ale_auth_listen_v6.htm
tech.root: netvista
ms.assetid: 8225be6d-b7a4-44db-bdff-bc223aa213c5
ms.date: 05/02/2018
ms.keywords: FWPS_FIELDS_ALE_AUTH_LISTEN_V6, FWPS_FIELDS_ALE_AUTH_LISTEN_V6 enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELDS_ALE_AUTH_LISTEN_V6_, FWPS_FIELD_ALE_AUTH_LISTEN_V6_ALE_APP_ID, FWPS_FIELD_ALE_AUTH_LISTEN_V6_ALE_PACKAGE_ID, FWPS_FIELD_ALE_AUTH_LISTEN_V6_ALE_USER_ID, FWPS_FIELD_ALE_AUTH_LISTEN_V6_FLAGS, FWPS_FIELD_ALE_AUTH_LISTEN_V6_INTERFACE_TYPE, FWPS_FIELD_ALE_AUTH_LISTEN_V6_IP_LOCAL_ADDRESS, FWPS_FIELD_ALE_AUTH_LISTEN_V6_IP_LOCAL_ADDRESS_TYPE, FWPS_FIELD_ALE_AUTH_LISTEN_V6_IP_LOCAL_INTERFACE, FWPS_FIELD_ALE_AUTH_LISTEN_V6_IP_LOCAL_PORT, FWPS_FIELD_ALE_AUTH_LISTEN_V6_LOCAL_INTERFACE_PROFILE_ID, FWPS_FIELD_ALE_AUTH_LISTEN_V6_MAX, FWPS_FIELD_ALE_AUTH_LISTEN_V6_SIO_FIREWALL_SOCKET_PROPERTY, FWPS_FIELD_ALE_AUTH_LISTEN_V6_TUNNEL_TYPE, fwpsk/FWPS_FIELDS_ALE_AUTH_LISTEN_V6, fwpsk/FWPS_FIELD_ALE_AUTH_LISTEN_V6_ALE_APP_ID, fwpsk/FWPS_FIELD_ALE_AUTH_LISTEN_V6_ALE_PACKAGE_ID, fwpsk/FWPS_FIELD_ALE_AUTH_LISTEN_V6_ALE_USER_ID, fwpsk/FWPS_FIELD_ALE_AUTH_LISTEN_V6_FLAGS, fwpsk/FWPS_FIELD_ALE_AUTH_LISTEN_V6_INTERFACE_TYPE, fwpsk/FWPS_FIELD_ALE_AUTH_LISTEN_V6_IP_LOCAL_ADDRESS, fwpsk/FWPS_FIELD_ALE_AUTH_LISTEN_V6_IP_LOCAL_ADDRESS_TYPE, fwpsk/FWPS_FIELD_ALE_AUTH_LISTEN_V6_IP_LOCAL_INTERFACE, fwpsk/FWPS_FIELD_ALE_AUTH_LISTEN_V6_IP_LOCAL_PORT, fwpsk/FWPS_FIELD_ALE_AUTH_LISTEN_V6_LOCAL_INTERFACE_PROFILE_ID, fwpsk/FWPS_FIELD_ALE_AUTH_LISTEN_V6_MAX, fwpsk/FWPS_FIELD_ALE_AUTH_LISTEN_V6_SIO_FIREWALL_SOCKET_PROPERTY, fwpsk/FWPS_FIELD_ALE_AUTH_LISTEN_V6_TUNNEL_TYPE, netvista.fwps_fields_ale_auth_listen_v6, wfp_ref_5_const_3_data_fields_2dfb65c6-8813-4193-bd8a-5fa5c2726633.xml
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Unless otherwise noted, supported starting with Windows Vista.
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
- fwpsk.h
api_name:
- FWPS_FIELDS_ALE_AUTH_LISTEN_V6
product:
- Windows
targetos: Windows
req.typenames: FWPS_FIELDS_ALE_AUTH_LISTEN_V6
---

# FWPS_FIELDS_ALE_AUTH_LISTEN_V6_ enumeration


## -description


The FWPS_FIELDS_ALE_AUTH_LISTEN_V6 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_ALE_AUTH_LISTEN_V6 and FWPS_LAYER_ALE_AUTH_LISTEN_V6_DISCARD 
  <a href="https://docs.microsoft.com/windows/desktop/FWP/management-filtering-layer-identifiers-">run-time filtering layers</a>



## -enum-fields




### -field FWPS_FIELD_ALE_AUTH_LISTEN_V6_ALE_APP_ID

The full path of the application.


### -field FWPS_FIELD_ALE_AUTH_LISTEN_V6_ALE_USER_ID

The identifier of the local user.


### -field FWPS_FIELD_ALE_AUTH_LISTEN_V6_IP_LOCAL_ADDRESS

The local IP address.


### -field FWPS_FIELD_ALE_AUTH_LISTEN_V6_IP_LOCAL_ADDRESS_TYPE

The local IP address type. The possible values are defined by the 
     <a href="https://docs.microsoft.com/windows/desktop/api/nldef/ne-nldef-nl_address_type">NL_ADDRESS_TYPE</a> enumeration.


### -field FWPS_FIELD_ALE_AUTH_LISTEN_V6_IP_LOCAL_PORT

The local transport protocol port number.


### -field FWPS_FIELD_ALE_AUTH_LISTEN_V6_IP_LOCAL_INTERFACE

The locally unique identifier (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/igpupvdev/ns-igpupvdev-_luid">LUID</a>) for the network interface associated with the
     local IP address.


### -field FWPS_FIELD_ALE_AUTH_LISTEN_V6_FLAGS

A bitwise OR of a combination of filtering condition flags. For information about the possible
     flags, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/filtering-condition-flags">Filtering Condition Flags</a>.


### -field FWPS_FIELD_ALE_AUTH_LISTEN_V6_INTERFACE_TYPE

The type of the network interface, as defined by the Internet Assigned Numbers Authority (IANA).
     For more information, see 
     <a href="https://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a>.


### -field FWPS_FIELD_ALE_AUTH_LISTEN_V6_TUNNEL_TYPE

The encapsulation method used by a tunnel if the 
     <b>IfType</b> member of the IP_ADAPTER_ADDRESSES structure is IF_TYPE_TUNNEL. The tunnel type is defined
     by IANA. For more information, see 
     <a href="https://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a> and the
     Windows SDK.


### -field FWPS_FIELD_ALE_AUTH_LISTEN_V6_LOCAL_INTERFACE_PROFILE_ID

The profile identifier (network category) of the network interface associated with the local IP
     address. The possible network category values are: public (1), private (2), or domain (3).
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_ALE_AUTH_LISTEN_V6_SIO_FIREWALL_SOCKET_PROPERTY

The IP_PROTECTION_LEVEL property associated with the socket.
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_ALE_AUTH_LISTEN_V6_ALE_PACKAGE_ID

The package identifier is a security identifier (SID) that identifies the associated AppContainer process. For more information about the SID structure, see the description for the SID structure in the Microsoft Windows SDK documentation.

<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_FIELD_ALE_AUTH_LISTEN_V6_ALE_SECURITY_ATTRIBUTE_FQBN_VALUE

The fully qualified binary name (FQBN) value of the application.

<div class="alert"><b>Note</b>  Supported starting with Windows 10.</div>
<div> </div>

### -field FWPS_FIELD_ALE_AUTH_LISTEN_V6_COMPARTMENT_ID

The compartment that the network interface belongs to.

<div class="alert"><b>Note</b>  Supported starting with Windows 10, version 1703.</div>
<div> </div>

### -field FWPS_FIELD_ALE_AUTH_LISTEN_V6_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/igpupvdev/ns-igpupvdev-_luid">LUID</a>



<a href="https://docs.microsoft.com/windows/desktop/api/nldef/ne-nldef-nl_address_type">NL_ADDRESS_TYPE</a>
 

 

