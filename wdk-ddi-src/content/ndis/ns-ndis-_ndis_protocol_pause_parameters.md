---
UID: NS:ndis._NDIS_PROTOCOL_PAUSE_PARAMETERS
title: _NDIS_PROTOCOL_PAUSE_PARAMETERS (ndis.h)
description: NDIS passes an NDIS_PROTOCOL_PAUSE_PARAMETERS structure to a protocol driver when it calls the ProtocolNetPnPEvent function to indicate a NetEventPause event.
old-location: netvista\ndis_protocol_pause_parameters.htm
tech.root: netvista
ms.assetid: 7754d47f-9e21-44c7-8a6f-141d18623ddf
ms.date: 05/02/2018
ms.keywords: "*PNDIS_PROTOCOL_PAUSE_PARAMETERS, NDIS_PROTOCOL_PAUSE_PARAMETERS, NDIS_PROTOCOL_PAUSE_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_PROTOCOL_PAUSE_PARAMETERS, PNDIS_PROTOCOL_PAUSE_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PROTOCOL_PAUSE_PARAMETERS, ndis/NDIS_PROTOCOL_PAUSE_PARAMETERS, ndis/PNDIS_PROTOCOL_PAUSE_PARAMETERS, netvista.ndis_protocol_pause_parameters, protocol_structures_ref_0b5004b2-d77f-427a-8473-f0ffb13a09f4.xml"
ms.topic: struct
f1_keywords:
 - "ndis/NDIS_PROTOCOL_PAUSE_PARAMETERS"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
- ndis.h
api_name:
- NDIS_PROTOCOL_PAUSE_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_PROTOCOL_PAUSE_PARAMETERS, *PNDIS_PROTOCOL_PAUSE_PARAMETERS
---

# _NDIS_PROTOCOL_PAUSE_PARAMETERS structure


## -description


NDIS passes an NDIS_PROTOCOL_PAUSE_PARAMETERS structure to a protocol driver when it calls the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a> function to
  indicate a 
  <b>NetEventPause</b> event.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_PROTOCOL_PAUSE_PARAMETERS structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_PROTOCOL_PAUSE_PARAMETERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_PROTOCOL_PAUSE_PARAMETERS_REVISION_1.


### -field Flags

Reserved.


### -field PauseReason

<div class="alert"><b>Note</b>  This member is deprecated for NDIS 6.40 and later drivers.</div>
<div> </div>
The value will always be NDIS_PAUSE_NDIS_INTERNAL.


## -remarks



To specify the pause parameters for a binding, NDIS passes a pointer to an
    NDIS_PROTOCOL_PAUSE_PARAMETERS structure to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a> function when
    NDIS indicates a 
    <b>NetEventPause</b> event.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a>
 

 

