---
UID: NS:fwpsk.FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0_
title: FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0_ (fwpsk.h)
description: The FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0 structure defines IPsec information associated with outbound packet data.Note  FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0 is a specific version of FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION.
old-location: netvista\fwps_packet_list_outbound_ipsec_information0.htm
tech.root: netvista
ms.assetid: 18312157-f41c-474d-9cf4-446d8b189c4d
ms.date: 05/02/2018
ms.keywords: FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0, FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0 structure [Network Drivers Starting with Windows Vista], FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0_, fwpsk/FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0, netvista.fwps_packet_list_outbound_ipsec_information0, wfp_ref_3_struct_3_fwps_P-Z_b5959556-81fe-4c93-9700-2214fee005c5.xml
ms.topic: struct
f1_keywords:
 - "fwpsk/FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0"
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
- FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0
product:
- Windows
targetos: Windows
req.typenames: FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0
---

# FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0_ structure


## -description


The <b>FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0</b> structure defines IPsec information associated with
  outbound packet data.
<div class="alert"><b>Note</b>  <b>FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0</b> is a specific version of <b>FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -struct-fields




### -field isIPsecPolicyMatch

A value that indicates whether the packet list matched an IPsec filter at the outbound transport
     layer.


### -field isTransportPolicyMatch

A value that indicates whether the packet list matched an IPsec transport mode filter at the outbound
     transport layer.


### -field isTunnelPolicyMatch

A value that indicates whether the packet list matched an IPsec tunnel mode filter at the outbound
     transport layer.


### -field isTunnelIPinIP

A value that indicates whether the packet list matched an IP-in-IP filter for IPsec tunnel mode.


## -remarks



An FWPS_PACKET_LIST_OUTBOUND_IPSEC_INFORMATION0 structure is included as a member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_packet_list_ipsec_information0_">
    FWPS_PACKET_LIST_IPSEC_INFORMATION0</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_packet_list_ipsec_information0_">
   FWPS_PACKET_LIST_IPSEC_INFORMATION0</a>
 

 

