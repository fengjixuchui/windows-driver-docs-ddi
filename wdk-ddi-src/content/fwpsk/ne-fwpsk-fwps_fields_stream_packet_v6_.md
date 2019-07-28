---
UID: NE:fwpsk.FWPS_FIELDS_STREAM_PACKET_V6_
title: FWPS_FIELDS_STREAM_PACKET_V6_ (fwpsk.h)
description: The FWPS_FIELDS_STREAM_PACKET_V6 enumeration type specifies the data field identifiers for the FWPS_LAYER_STREAM_PACKET_V6 run-time filtering layer.
old-location: netvista\fwps_fields_stream_packet_v6.htm
tech.root: netvista
ms.assetid: fa2a415d-11be-49f1-ad93-975c25f3db07
ms.date: 05/02/2018
ms.keywords: FWPS_FIELDS_STREAM_PACKET_V6, FWPS_FIELDS_STREAM_PACKET_V6 enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELDS_STREAM_PACKET_V6_, FWPS_FIELD_STREAM_PACKET_V6_DIRECTION, FWPS_FIELD_STREAM_PACKET_V6_FLAGS, FWPS_FIELD_STREAM_PACKET_V6_INTERFACE_INDEX, FWPS_FIELD_STREAM_PACKET_V6_INTERFACE_TYPE, FWPS_FIELD_STREAM_PACKET_V6_IP_LOCAL_ADDRESS, FWPS_FIELD_STREAM_PACKET_V6_IP_LOCAL_INTERFACE, FWPS_FIELD_STREAM_PACKET_V6_IP_LOCAL_PORT, FWPS_FIELD_STREAM_PACKET_V6_IP_REMOTE_ADDRESS, FWPS_FIELD_STREAM_PACKET_V6_IP_REMOTE_PORT, FWPS_FIELD_STREAM_PACKET_V6_MAX, FWPS_FIELD_STREAM_PACKET_V6_SUB_INTERFACE_INDEX, FWPS_FIELD_STREAM_PACKET_V6_TUNNEL_TYPE, fwpsk/FWPS_FIELDS_STREAM_PACKET_V6, fwpsk/FWPS_FIELD_STREAM_PACKET_V6_DIRECTION, fwpsk/FWPS_FIELD_STREAM_PACKET_V6_FLAGS, fwpsk/FWPS_FIELD_STREAM_PACKET_V6_INTERFACE_INDEX, fwpsk/FWPS_FIELD_STREAM_PACKET_V6_INTERFACE_TYPE, fwpsk/FWPS_FIELD_STREAM_PACKET_V6_IP_LOCAL_ADDRESS, fwpsk/FWPS_FIELD_STREAM_PACKET_V6_IP_LOCAL_INTERFACE, fwpsk/FWPS_FIELD_STREAM_PACKET_V6_IP_LOCAL_PORT, fwpsk/FWPS_FIELD_STREAM_PACKET_V6_IP_REMOTE_ADDRESS, fwpsk/FWPS_FIELD_STREAM_PACKET_V6_IP_REMOTE_PORT, fwpsk/FWPS_FIELD_STREAM_PACKET_V6_MAX, fwpsk/FWPS_FIELD_STREAM_PACKET_V6_SUB_INTERFACE_INDEX, fwpsk/FWPS_FIELD_STREAM_PACKET_V6_TUNNEL_TYPE, netvista.fwps_fields_stream_packet_v6, wfp_ref_5_const_3_data_fields_c50e3f20-5176-49dc-8cd4-81384cd07568.xml
ms.topic: enum
f1_keywords:
 - "fwpsk/FWPS_FIELDS_STREAM_PACKET_V6"
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 7.
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
- FWPS_FIELDS_STREAM_PACKET_V6
product:
- Windows
targetos: Windows
req.typenames: FWPS_FIELDS_STREAM_PACKET_V6
---

# FWPS_FIELDS_STREAM_PACKET_V6_ enumeration


## -description


The FWPS_FIELDS_STREAM_PACKET_V6 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_STREAM_PACKET_V6 
  <a href="https://docs.microsoft.com/windows/desktop/FWP/management-filtering-layer-identifiers-">run-time filtering layer</a>.


## -enum-fields




### -field FWPS_FIELD_STREAM_PACKET_V6_IP_LOCAL_ADDRESS

The local IP address.


### -field FWPS_FIELD_STREAM_PACKET_V6_IP_REMOTE_ADDRESS

The remote IP address.


### -field FWPS_FIELD_STREAM_PACKET_V6_IP_LOCAL_PORT

The local transport protocol port number.


### -field FWPS_FIELD_STREAM_PACKET_V6_IP_REMOTE_PORT

The remote transport protocol port number.


### -field FWPS_FIELD_STREAM_PACKET_V6_IP_LOCAL_INTERFACE

The locally unique identifier (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/igpupvdev/ns-igpupvdev-_luid">LUID</a>) for the network interface associated with the
     local IP address.


### -field FWPS_FIELD_STREAM_PACKET_V6_INTERFACE_INDEX

The index of the network interface, as enumerated by the network stack.


### -field FWPS_FIELD_STREAM_PACKET_V6_SUB_INTERFACE_INDEX

The index of the logical network interface, as enumerated by the network stack.


### -field FWPS_FIELD_STREAM_PACKET_V6_DIRECTION

The possible values are:

<ul><li>FWP_DIRECTION_INBOUND</li><li>FWP_DIRECTION_OUTBOUND</li></ul>


### -field FWPS_FIELD_STREAM_PACKET_V6_FLAGS

A bitwise OR of a combination of filtering condition flags. For information about the possible
     flags, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/filtering-condition-flags">Filtering Condition Flags</a>.


### -field FWPS_FIELD_STREAM_PACKET_V6_INTERFACE_TYPE

The type of the network interface, as defined by the Internet Assigned Numbers Authority (IANA).
     For more information, see 
     <a href="https://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a>.


### -field FWPS_FIELD_STREAM_PACKET_V6_TUNNEL_TYPE

The encapsulation method used by a tunnel if the 
     <b>IfType</b> member of the IP_ADAPTER_ADDRESSES structure is IF_TYPE_TUNNEL. The tunnel type is defined
     by IANA. For more information, see 
     <a href="https://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a> and the
     Windows SDK.


### -field FWPS_FIELD_STREAM_PACKET_V6_COMPARTMENT_ID

The compartment that the network interface belongs to.

<div class="alert"><b>Note</b>  Supported starting with Windows 10, version 1703.</div>
<div> </div>

### -field FWPS_FIELD_STREAM_PACKET_V6_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/igpupvdev/ns-igpupvdev-_luid">LUID</a>
 

 

